---
description: Step by step guide on how a ticket goes from development to deploy to test.
---

# ticket journey

## Development to deploy

1. Developer works on task assigned within ticket, developing locally, on a branch. 
2. Development finishes and the branch is pushed. 
3. Developer creates merge request in gitlab assigning to tech reviewer \(default Giles\) \(unless on master branch\).
4. Tech reviewer reviews and merges / raises comments / discussions as appropriate.
5. Once merged, release manager \(Giles\) tags a new version and pushes to build new image. This may be delayed if multiple changes happening at same time.
6. Once built, new version deployed to Staging.
7. Once deployed to Staging, ticket moved to "QA" column and assigned to QA team \(default Jan\). 

## Quality assurance testing

### Test

1. QA testing performed on the ticket. 
2. QA report added to the ticket. 

### Fail   

1. Ticket re-assigned to Developer if it fails testing and moved back to "In Progress" column.
2. Back to Stage 1 of Development process \(see above\).

### Pass

1. If the ticket passes QA it is then placed into "UAT" column to be reviewed in the next Show & Tell session. 



