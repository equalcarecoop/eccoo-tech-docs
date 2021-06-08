---
description: This page describes the focus of the MVP related to team management
---

# team management

## Business needs

Equal Care Facilitators are taking a large amount of time managing teams in the current tactical platform. By providing the ability to form and expand teams within the platform, this removes some of the burden from facilitators.

## Overview

There are three parts to team formation:

* Creating a team when the person getting support \(or the person acting on their behalf\) invites the first person giving support
* Extending a team by inviting additional team members
* Joining an existing team by requesting access

In each case, this is a two-part activity, either invite-accept \(initiated by the person getting support\), or request-approve \(initiated by the person giving support\).

1. The system **must** present lists of pending invitations and requests to all relevant parties, enabling acceptance / approval as appropriate.
2. The system **will** only allow a person getting support or their advocate \(albeit that in reality this is being 'faked' by current users given lack of a specific arranging support hat\) to approve requests.
3. The system **will** only allow a person giving support to accept their own invitations.
4. The system **should** notify the all parties via direct message of changes in state.
5. The system **should** keep Rocket Chat team membership aligned to the confirmed team members.

## Use cases

{% hint style="warning" %}
The use cases below assume that invitations/requests are either accepted/approved or ignored. The sunny-day scenario is the only one presented. Logically, there may also be alternative scenarios which enable declined/rejected outcomes.
{% endhint %}

### Team arranger adds a new person giving support to the team

Team arranger is the team owner \(person getting support\) or the person arranging support on their behalf.

#### Preconditions

* All relevant people registered in system.
* Team may or may not yet exist.
* All relevant hats requests have been granted.

#### Steps

1. System presents a search for user form
2. Team arranger searches for team member by name
3. System presents a list of matching platform users with a giving support hat, along with minimal contextual summary
4. Team arranger selects the team member and invites them to their team
5. System notifies team arranger of outcome of request

#### Postcondition

* System has created a record for team \(if one did not exist\)
* System has registered invitation for potential team member
* System \(potentially\) notifies potential team member via Rocket Chat.

### Person giving support accepts invitation to team

#### Preconditions

* An invitation has been sent

#### Steps

1. System presents list of pending invitations
2. User selects invitation from list of invites
3. System presents details of the invitation including team summary
4. User accepts the invitation
5. System notifies person giving support of outcome

#### Postconditions

* Person Giving Support is added to the team
* Team members can see one another's profiles on the team page
* Team Arranger is notified that invitation has been accepted

### Person giving support requests access to join an existing team

#### Preconditions

* A team exists
* Person Giving Support has been granted hat

#### Steps

1. System presents a search form for teams
2. Person Giving Support searches for a team by team owner name
3. System presents a list of matching teams
4. Person Giving Support selects the team they wish to join
5. System confirms that the request has been made

#### Postconditions

* System has created a record of the request to join a team
* The team owner / arranger has been notified of the request

### Team arranger approves request to join a team

#### Preconditions



#### Steps



#### Postconditions







