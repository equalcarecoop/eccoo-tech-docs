---
description: Steps for restoring a backup of the rocket chat database
---

# Restoring chat-db backups

On the off-chance that something terrible happens with our chat service, we can restore backups easily in a few steps. This playbook talks you through how to do it at a high level - details should be filled in if/when necessary in the future by anyone who finds it difficult to follow.

### Restoring the backup to a directory on EFS&#x20;

1. Visit the [EFS dashboard](https://eu-west-2.console.aws.amazon.com/efs/home?region=eu-west-2#/file-systems). Find the volume ID and make a note of it (or leave it open in a tab etc.).
2. Visit the [Backup dashboard](https://eu-west-2.console.aws.amazon.com/backup/home?region=eu-west-2#/resources). Find the backup for the volume with the matching ID. Select the recovery point that you want and press the 'restore' button. This creates a new, timestamped directory inside the volume and won't affect running services.

### Find the backup directory

1. Create a throwaway EC2 instance that we'll use to inspect the EFS volume. Make sure to place in the same VPC and attach the correct EFS during creation.
2. SSH onto the EC2 instance and navigate to the EFS mount.
3. Find the directory with the restored backup - it will be of the form `aws-backup-restore<timestamp>`.

### Move the task definition volume to point to the new directory

1. Alter the cloudformation template for the chat db service to point to the backup directory as the new root directory.
2. ```
   diff --git a/roles/rocket-chat/files/chat.cf.yaml b/roles/rocket-chat/files/chat.cf.yaml
   index 7f34d64..bf164bf 100644
   --- a/roles/rocket-chat/files/chat.cf.yaml
   +++ b/roles/rocket-chat/files/chat.cf.yaml
   @@ -223,6 +223,7 @@ Resources: 
      - Name: chat-db
        EFSVolumeConfiguration:
          FilesystemId: !Ref DbStorage
   +      RootDirectory: aws-backup-restore_2022-01-17T08-53-32-695Z
      - Name: chat-dump
        EFSVolumeConfiguration:
          FilesystemId: !Ref DumpStorage
   ```

3\. Deploy the new task definition. Manually kill the existing chat db task when necessary to allow the new task to be created.

### Cleanup

There are a number of things to clean up here including:

1. the throwaway EC2 instance
2. checking in the volume configuration to GitLab
3. cleaning up the volume directories so that we don't end up with an ever-growing, nested directory chain for backups. This needs investigating when we **actually** do this for the first time but it's not necessary to restore functionality in the event of an emergency.

