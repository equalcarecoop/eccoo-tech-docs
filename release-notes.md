# release notes

## 2021-05-06

### Features and fixes

* Identity and access / Keycloak
  * Styling changes to login pages
* UI
  * Further fixes to copy and to correctly display all location options in getting summary narrative.
  * Fix profile builder progress completed sections logic.
  * Fix rates handling from QA issues.
  * Move cancel button for update account details onto form.
  * Move contextual to right hand side within appropriately formatted box.

**Known defects**

* The contextual help is boxed and to the right of the forms but the flow for breakpoints is not quite right and will be picked up in an overall review of layout post 1st drop.

### Status of Rocket Chat

This release includes integration with a vanilla instance of Rocket Chat, which has some of the styling that Austin worked on applied via a supported Rocket Chat mechanism. The approach that we trialled with Austin would have likely resulted in a maintenance overhead, and significant version drift from the latest Rocket Chat.

Users log in with their EqualCare identities (i.e. keycloak identities) and are allocated RC roles based on groups set up in Keycloak. At the moment, this is limited to Emma and Giles being admins, but we can broaden this out to as many roles as we need within RC. Discussion required around this.

In this release, no channels are automatically created. This would be a useful spike to look at (Create channels for team chat and manage user membership of the channel). There is a question over automation vs manual management of groups. I suspect this will end up being a hybrid model.

#### Known Defects

* Rocket Chat mobile app (iOS / Android) is not yet working. This appears to be a known issue that has been solved by some people implementing. Investigations continue.
* ~~Rocket Chat can under certain circumstances show the messages of a previously logged in user. This will only occur if the current user is on the same physical device using the same browser as the previous user.~~** Fixed**

### Change log for ui-v1 since v0.32.6

```
09f1d55 fix handling rates rounding on new profile
a0170e3 fix:handling of rates in view when none entered
acc423f fix error on rates plus move cancel button into update account form
8b3c609 fix:handling rates when none yet entered
d8165f8 fix:move cancel button onto update account form
d8c8f29 chore: style the guidance boxes
1a3194a 0.33.2
35b9dbb fix: clear rocket chat session
a7d1bd5 correctly handle rates with more than 2 decimal places
795b7ce fix:handling rate rounding errors
d51105a 0.33.0
8307ebb feature: add info route to report version of code
24f5587 fix:radio button formatting
a7375b2 fix:progress complete sections for giving
bb18221 fix:progress complete sections for getting
361e294 fix:correct summary  location details, clear unset
0d1f7d1 0.32.7
d7a2ca8 fix:update guidance with links
45e6808 fix:retain areas covered entries on form errors
0bf10ed fix:copy typo
8cbfbdc fix:display currency with 2 decimal places
1916d52 fix:update to rates rather than adding additional
7326b2d fix: handle decimal input to minutes fields
```

### Change log for graph-api since v0.31.0

```
```

### Change log for identity-access since v0.10.1

```
80ecaf6 0.11.2
a459ecf fix:layout of hyphen on register page
e3d90c0 0.11.1
d1b34ef fix:change styling to gradient tick circle
79289dc chore:update verify email copy
cdf0db3 0.11.0
b63620d chore: add name to package.json
976b3ba chore:copy changes for login pages
c74a22d chore:sign in options increase font size
```

## 2021-04-27

```
  2020-04-27:
    keycloak:  v0.10.1
    graph_api: v0.31.0
    ui:        v0.32.6
```

### Features and fixes

* UI
  * Account details - correct validation of phone numbers; additional emergency contact details; correct amending of preferred name; improved layout allowing multiple columns on form and display; add alternative phone number field, date of birth date picker to GDS style three box input with appropriate validation; persistence of address details on validation errors. My account and update copywriting as per matrix.
  * Account section - change ordering and layout for policies and roles sections; including open policy links in new window.
  * Copywriting and layout changes for hello pages, invitation code, postcode and giving getting selection pages. Embed leave details jotform.
  * Getting support profile - hide when section and key documents section; add personal care question to introduction to enable conditional questions; add additional fields as per copy matrix to physical & mental wellbeing, relationships & community, where support takes place; update copy and layout for all forms as per matrix. Update getting profile summary with narrative introductory paragraph and pulling through all additional or modified fields from forms.
  * Giving support profile - hide availability section and add in supporting me section; add free text date achieved field for qualifications; add checkbox copy/options for expertise, physical & mental wellbeing, relationships & community, surroundings; add and amend fields in travel, money & time. Include icons with profile summary introductory paragraph.
  * Multiple changes related to build optimisation
  * Rocket chat login management
* Graph
  * Add database setup / migrations control
  * Change API to cover additional profile elements required via the content changes

### Change log for ui-v1 since v0.24.2

```
9770a20 0.32.6
f9c7802 chore: adding back ght actual build step
2223ea9 0.32.5
3587a01 chore: revert to original docker build
4f5bb98 0.32.4
c604091 chore: fix tags
c49c7bd 0.32.3
f0d6e82 build: switch to kaniki builder
b114bdb 0.32.2
92f972c chore: fix the build
07908bc 0.32.1
6f4cf27 chore: attempt to speed up builds
a4ad413 chore: fix more security advisories in npm modules
dd42f8a chore: update security issues
d325bfb chore: change to @mr-hope/gulp-sass
f532139 fix:change support I need to support I get
7329390 fix: open policy pages in new window
d7f0d24 0.32.0
6a5904d fix:correct order of add/display qualifications
98a28f6 chore:code tidy
af9e746 feat:travel moeny time functionality and display
b7529d8 feat:travel money time functionality
f0b9f45 0.31.0
53dd095 feature: initialise primary location with postcode
0a39ff6 fix: redirect from /messages/sso if not in iframe
0f007c4 feature: switch to oauth login for Rocket Chat
059134d feat:additional travel money time functionality
c17d2ea chore:remove debug easter egg
5ac73de feat:qualifications date achieved plus tech debt
f0a8112 0.30.2
bca57ae fix: clean up chat auth flow
42057d7 0.30.1
bdb1b35 fix: turning off report only CSP
dfc5bb2 0.30.0
39465b1 feature: add csp report endpoint
56ad6ab chore:copy update giving preferences
ad3e0d1 chore:copy update giving approach
65bedf8 chore:copy update giving whats important
d5464fa chore:copy changes surrounding
ef9e0a4 fix:pull through existing relationship choices
9777338 chore:copy changes relationships community
c4cde9d chore:copy changes physical mental wellbeing
a3d0e52 chore:giving experience copy and tech debt
c3c4672 chore:giving expertise copy and tech debt
5e2cc6d chore:remove avatar from giving summary
4fc0ba0 Merge branch 'master' of gitlab.com:eccoo-platform/services/user-interface-v1
2735209 chore:giving introduction copy update & tech debt
4a2c881 fix: enable rocket chat sign-in
bf21551 fix: allow image-src from any equalcare.coop site
3e00890 Merge branch 'chore/giving-support-summary-page-copy-changes'
02212d7 0.29.0
5438d4e feat:implement supporting me section & update
b341d62 chore: make tests relative to origin/master
f54f6e4 fix: allow rocket chat in content security policy
c3cfd36 chore:start supporting me form construction
f577958 feat:supporting me set up on giving
d6092cf feat:disable availability section
59a6805 chore:section title changes
2a84c51 chore:remove summary reformat intro
4c4e868 chore:changes to giving summary information
4c964e8 chore: prevent Google tracking with FLoC
cbad6fb chore: updates helmet middleware
44fd943 Merge branch 'feat/show-fields-on-select' into 'master'
dbc3222 fix: rendering of other location details
2bd5ad2 feat:dependent fields medicine mobility support
b8fabd0 chore:change input to single line text
8262781 feat: dependent inputs on location page
b4867a8 Fix for update account details when no locations
6880a37 fix:handling empty address
fd81ca1 Display all location combinations properly in profile summary
bfe2cbe fix:all location combinations and internationalise
16e6788 chore:internationalise location options
94d39e3 fix: additional location combinations
f04719a fix: all location combinations
964773d 0.28.0
7493923 Merge branch 'feature/copywriting-and-implementation-for-getting-profile-builder' into 'master'
7408d18 Merge branch 'feature/additional-getting-location-options' into 'master'
fa88ccc Merge branch 'feature/copy-writing-for-follow-up-pages' into 'master'
1fe67b7 feat: embed leave details jotform in follow up
09b4d6c chore: fix borken tests
4ef619c chore: limit tests for git push
0502b82 Merge branch 'feature/additional-fields-and-toggles-for-physical-mental-wellbeing' into 'master'
b951283 fix: sort message logic
c2d6b2f feat:additional location options
6c8c2d9 chore:swap labels for led vs led axis
1f6e143 feat:support from others field added to getting
2a1eef7 chore:additional field support needs relationships
b787e7d 0.27.1
b7723af Merge branch 'fix/address-details-persist-on-vlaidation-error' into 'master'
af14e31 chore:code tidy
731712c fix:address details not lost on validation errors
96f2088 chore:remove txt field if toggle unset tidy format
f1a71aa feat/physical and mental wellbeing per copy matrix
dafd462 chore:create fields on form with copy from matrix
05807a7 fix: move contextual help to right and box
f481118 chore:copy for personal care  in a bit about me
706b806 chore: copy for personal care requirements
7ac166e chore: hide key documents section for first drop
08de1ad chore: profile summary - preferred name as title
4ef5283 fix: error message email link correction
8951b39 fix: invalid invitation code follow up
7269518 0.27.0
29d9f66 Merge branch 'feat-implement-GDS-style-date-picker' into 'master'
661a8a9 fix: add error messages lost in merge
0a97bb9 fix: merge conflicts
089a0f5 Merge branch 'feat-implement-GDS-style-date-picker' of gitlab.com:eccoo-platform/services/user-interface-v1 into feat-implement-GDS-style-date-picker
6bd9eee fix: clear all merge conflicts
31397ad fix:conditional validation of alternative number
1bc74cd fix: correct layout from merge conflict
0fecf48 fix: resolve merge conflicts
ed1a2dd fix: error handling for min age 16 years
6576db0 wip: try catch tb completed
45c35b0 feat:implement (GDS pattern) 3 box date input
520be5f chore:sorting out handling and validation
01809a9 chore:wire in dob date picker
5d50c91 chore: implement required fields validation errors
9ca26c4 feat: add optional alternative phone number field
13194cd fix: error handling for min age 16 years
4477d3a wip: try catch tb completed
97ef47f wip: pipe transformer exception age less than 16
408417a chore: fix tests
5a72e78 fix: correct date of birth map for errors
962c449 fix: correct year handling on 3 box date input
1d548a8 feat:implement (GDS pattern) 3 box date input
f0ca483 chore:sorting out handling and validation
1fb76a9 chore:wire in dob date picker
5922b8e Merge branch 'feature/208-further-copywriting' into 'master'
2824ba3 fix: error handling for min age 16 years
00b5808 wip: try catch tb completed
04a05c7 wip: pipe transformer exception age less than 16
8497073 chore: tidy unused code
2d62f77 feat: copy and layout updates for account sections
3b42f85 chore: call all cancel buttons from same json
09f675a chore: tidy policies page with secondary buttons
0dc4ddb chore: change order of LH links
e72b62f chore: add example to date of birth label
4fc646e chore; remove uneditable fields from form
07a3c8c fix:make alternative number optional but validated
15cfcce chore: fix tests
bbf364a fix: correct date of birth map for errors
1bb4cd0 Merge branch 'feat/enable-additional-phone-number' into 'master'
54c1ea2 chore: implement required fields validation errors
0c27da8 feat: add optional alternative phone number field
6e58ffb chore: pull through email address from keycloak
a200f9d fix: correct year handling on 3 box date input
a65afe7 feat:implement (GDS pattern) 3 box date input
9d498dd chore:sorting out handling and validation
48ebeff chore:wire in dob date picker
1e6f93b Added time input picker and three and four columns for form layouts
180895c Merge branch 'feature/colums-and-circles' into 'master'
abf6095 feat: Added time input to form macro and implemented three and four columns for form layouts.
86e9617 account layout updates, new date picker, initial copywriting
577edf8 Merge branch 'feature/valid-forms' into 'master'
b55e00e feat: Added date inputs to form macro and implemented valid forms with labels.
74d046c feat:move adding personal care needs into intro
ba231a4 chore:copywriting getting where
becb782 chore:copywriting getting preferences
a239f30 chore:copywriting approach guidance
ce54d5b feat:add common choices - support with environment
274f335 chore:copywriting support needs relationships
bea0079 chore:copywriting support needs person
aeeb720 feat:wip key documents instead of essentials
7f6e480 chore:change to where personal care needs captured
6372ebf chore:update hats title and contextual help
5596ece chore: copywriting getting summary  as paragraph
624b4b0 chore:copywriting whats important
da23429 chore:copywriting intro guidance
b43e3bb chore:disable getting when as copy matrix comments
03a04a1 chore: copywriting getting support profile page
be0de29 chore: copywriting follow up pages
6cb9933 chore: copywriting for hats
37c3c01 chore: copywriting for policies
e838c17 chore: copy and formatting for policies link
e8a442d chore: account and update copy writing
83a8ce0 chore:i18n of suppport summary page
193847c chore: copy writing 404 error page
751215f chore: copy writing for first sign up stages
8abe282 chore: copy for hello page
4cb20c6 chore: amend nav bar sections
f638f5d Merge branch 'fix/issues-with-travel-money-time' into 'master'
d80ec96 style: Tidied up support and account form layouts and added ability to have two col form inputs to save vertical space, also fixed bug that was hiding close link for account edit page.
0e7adf8 chore:keep exisiting data if validation erros
f5012a5 fix:correctly display minimum booking duration
bc4d41e 0.26.4
8b0ae69 fix: ensure rocket chat and ui users in sync
fc5318d fix: ensure rocket chat and ui users in sync
f2631e6 chore: remove dependency on deprecated function
0121bfe fix: chat interceptor tests
8e68337 0.26.3
eb3892c fix: make JWT module global
3d90b93 0.26.2
9fc8ae4 fix: require authentication to access messages
468d282 0.26.1
ff64004 chore: externalise config for rocket chat
c6456fd 0.26.0
ed7f0ab feature: Implement SSO for rocket chat
4a6be61 feature: add iframe embed of rocket chat
60df174 styling improvements and enhanced emergency contact details
2c51cef Merge branch 'feat/668-additional-emergency-contact-fields' into 'master'
431a8ec Merge branch 'chore--i18n-experience-macro' into 'master'
315337f Merge branch 'master' into 'chore--i18n-experience-macro' Resolve conflicts # Conflicts: #   views/macros/profile-summary.njk #   views/partials/profile/giving-support/experience.njk
4530737 Merge branch 'feature/form-layouts' into 'master'
439fb5b feat: Updated FE kit version.
21ff89f Merge branch 'master' into feature/form-layouts
b0588d1 style: Updated edit forms for giving and getting and updated output formatting.
2b43cbb chore: implement i18n on display experience
dfa81a4 feat: additional emergency contact fields
6d50977 0.24.4
f8250c7 Merge branch 'bugfix/mobile-forms' into 'master'
433ec93 fix:merge conflict
f5e4157 fix: fixing merge conflicts
8432b4b fix: Fixed spacing issues with date edit form on mobile and other mobile styling fixes, with updated FE kit.
17ed207 0.24.3
4585c89 Merge branch 'chore/field-validation-for-phone-number-and-emergency-number' into 'master'
906c63a chore:remove commented code
88cf97d fix: change is phone number region to GB
d21f50f Merge branch 'fix/update-FE-toolkit' into 'master'
b7a6cda Merge branch 'chore-validation-for-start-end-times' into 'master'
d56085a Merge branch 'fix/preferred-name-input-issue' into 'master'
236e7dd fix:update emergency contact label  per QA comment
e82e191 chore: code lint
4cb65a1 fix: update npm to allow lockfileVersion 2
bd5f1e1 Fix:Update to latest version of FE kit
c814b23 chore: cross validation so end must be after start
e7edace chore:lint code
fe2aff8 fix:correct classes so input editable in mid size
```

### Change log for graph-api since v0.25.1

```
6612bb3 Add travel money time fields
f3bad23 fix:quallifcation date acheived can be nullable
f1360c8 feat:travel money time additional fields
96c90e8 0.30.0
a99b84a feat:qualifications date achieved
6e87ceb 0.29.0
82084dc feat:enable supportingMe field on giving
284d509 0.28.0
c5ce221 Merge branch 'feat/additional-toggles-for-getting' into 'master'
7a83860 feat: additional getting fields implementation
7170adb feat:additional field in relationship needs
0a82a3c feat:enable additional toggles and fields getting
e40d82f refactor: move keycloak jwt to libs
3519bf9 Fix driver close in migration
af12735 fix: leave driver open during migration
90755fc Add neo4j migrations
97618e3 feature: add migrations to startup
a1f2216 refactor: move neo4j to NestJS library
2ffb140 Merge branch 'feat/add-alternative-number-to-contact-details-enum' into 'master'
db51faa feat: alternative phone number
5cc7ad2 0.26.0
168cc4e Merge branch 'feature/668-additional-emergency-contact-fields' into 'master'
48de117 feat:enable additional emergency contact fields
```

### Change log for identity-access since v0.10.0

```
976b3ba chore:copy changes for login pages
c74a22d chore:sign in options increase font size
4a3993d Copy for register and log in
13d8ef3 chore:copy writing register and sign in
e4ef123 chore: switch from gulp-sass
```

## 2021-03-12-1

```
  2020-03-12-1:
    keycloak:  v0.10.0
    graph_api: v0.25.1
    ui:        v0.24.2  
```

### Features and fixes

* Fix error handling to only display errors from the page
* Styling fixes for overlapping on modal header, background circle images
* Check postcode is correct format before submitting and report errors
* Change checkbox entry to be only on pressing enter not on pressing tab, for accessibility reasons ([https://webaim.org/techniques/keyboard/](https://webaim.org/techniques/keyboard/))
* Limit preferred name to 50 characters (to avoid exceeding keycloak character limits)



### Change log for ui-v1 since v0.24.0

```
1ef95a9 Merge branch 'fix/limit-preferred-name-input-for-keycloak' into 'master'
76174f7 fix: use class-validator for max length
5afac1f Merge branch 'fix/remove-tab-key-input-for-adding-check-box' into 'master'
6442547 Merge branch 'Fix--postcode-entry-error-handling' into 'master'
95d4914 fix: use class-validator to check postcode
90b1565 chore:set pref name input limit at 50 characters
4300bc6 chore: improve accessibility
5ba2a56 0.24.1
5627df5 chore: errors handling and format update account
b4dc035 fix: limit input lenght on pref name handle errors
96ceb55 chore: add maxLength to preferred name input
cc82830 fix: add check box only on enter from qa feedback
2f4b74d fix: clean postcode entry prior to postcodejs
22707df Merge branch 'chore/improve-error-handling' into 'master'
b0d8a60 chore: add note on why includes to controllers
5b602f6 fix: handling of errors on page into controllers
74cd5de fix: do check for page in controller
8ac896b Merge branch 'bugfix/edit-modals' into 'master'
c32142b style: Updated FE kit package
53cf64b fix: Added missing circle divs to modal footer.
6321dfc fix: Updated fE kit styling to fix bugs with modal header being overlapped and progress blobs issue in Safari.
464166f chore: replace listerrors with listerrorsonpage
b689951 feat: only display errors relevant to page
```

### Change log for graph-api since v0.25.0

```
832951b 0.25.1
0cc94d5 fix: non-nullable preferences array cypher
```



## 2021-03-11

```
  2020-03-11:
    keycloak:  v0.10.0
    graph_api: v0.25.1
    ui:        v0.24.0
```

### Features and fixes

* Various fixes including error validation

### Change log for ui-v1 since v0.23.0

```
2860a21 0.24.0
cc41346 Merge branch 'feat/add-new-checkbox-on-enter-or-tab' into 'master'
8e044d3 Merge branch 'chore/snag-listing' into 'master'
b5ed543 feat: checkbox entries added by using enter or tab
c789c72 chore: i18n for TTM error messages
c1aa5a7 fix: error handling on travel money and time input
649a830 chore: wip error handling on ttm form
9d9b390 chore: tidy travel money time summary
5fff3d8 chore: tidy giving support summary
0975a02 chore: add error handling on to when form
8aff674 fix: correct approaches on getting profile
a85e4db fix: complete blob for needs relationships
bb37898 fix: remove dead link
c8bbeef chore: tidy i18n refs
```

### Change log for graph-api since v0.25.0

```
832951b 0.25.1
0cc94d5 fix: non-nullable preferences array cypher
```

## 2021-03-04

```
  2020-03-04:
    keycloak:  v0.10.0
    graph_api: v0.25.1
    ui:        v0.22.0
```

### Features

* Error page (custom for 404, with a default 'something went wrong')
* Background blobs
* Complete Giving Support edit pages (preferences and what's on)
* Added modal template to more Giving Support edit pages

### Fixes

* Many minor fixes

### Known issues / omissions:

* URLs still to be remapped in `/profile/giving-support` edit screens. In fact, quite a lot of tech debt here
* Should hide stack-trace in error page for production environments
* No error fields on giving Travel Money Time

### Change logs

#### ui-v1 since v0.21.0

```
808c529 0.22.0
9700f2e chore: fix a broken test in profile editor
a47860c Merge branch 'feature/background-shapes' into 'master'
0c03cd8 Merge origin/feature/186-giving-preferences into master
73e89d3 Merge branch 'feature/183-giving-whats-important' into 'master'
cd5127c Merge branch 'fix/location-progress-circle-getting' into 'master'
54f3eaa Merge branch 'chore--implement-testingModuleFactory-across-controllers' into 'master'
307cad5 feature: add error page
c5fa471 refactor: collect context providers into module
0a952df refactor: move all error handlers into module
54f2dbd fix: Fixed merge conflict in package lock after merging in master branch.
dad378f feat: Made most edit sections use modal template and added blocks to style with background circles.
00629cd chore: completeness test
165018b chore: to and fro with graphql
45cca1a chore: creating preferences giving route
e4d7773 feat/crupdate whats important
8d2b719 feat: giving support whats important
d82d68b fix: for circle not showing on location progress
c14786f chore:location revert to testingModuleFactory
db0f4de chore:whats important revert testingModuleFactory
de9d1b5 0.21.1
953f60f feature: remove lockin to follow-up
c9fb981 fix: incomplete tests for sign-up controller
ffde4fd chore: getting person revert testingModuleFactory
ce86031 chore: enviornment revert to testingModuleFactory
efb66a8 chore: relationships revert testingModuleFactory
1288644 chore: availability revert to testingModuleFactory
563eab7 chore: experience revert to testingModuleFactory
7555fd7 chore: expertise revert to testingModuleFactory
ee07804 chore: intro revert to testingModuleFactory
2538935 chore: quals revert to testingModuleFactory
d8c2d68 chore: ttm revert to testingModuleFactory
68d2f7c chore: approach revert to testingModuleFactory
aab4c79 chore: essentials revert to testingModuleFactory
c78ef8e chore: preferences revert to testingModuleFactory
5291510 style: Updating background shapes to be random based on body class.
```

#### graph-api since v0.25.0

```
832951b 0.25.1
0cc94d5 fix: non-nullable preferences array cypher
```

#### Change log for graph-api since v0.24.0

```
832951b 0.25.1
0cc94d5 fix: non-nullable preferences array cypher
56bce3d 0.25.0
cb2fa4a Merge branch 'feature/183-186-giving-whats-important-preferences' into 'master'
c311a6a feature: graph changes for prefs & whats important
90b191f 0.24.2
fe761a1 fix: remove incorrect gql mapping to cypher
2840a72 0.24.1
5d78c7f fix: return valid profile if available
```

## 2021-03-03

```
  2020-03-03:
    keycloak:  v0.10.0
    graph_api: v0.24.2
    ui:        v0.21.0
```

### Major Changes

* Added Person / Relationships / Environment forms for both Giving and Getting support
* Added invitation code and follow-up screens for sign-up (both need reviewing). Refactored the sign-up process to enforce valid code and covered postcode. (It was previously possible to leap steps in the process. No longer!)
* Added field-level validation to Giving Support Travel Money Time page

### Minor fixes:

* Fixed issue of null profile returned from graph in valid Giving / Getting Support query.
* Fixes to issues around supportApproaches

### Known issues / omissions:

* Potential issue with getting stuck on signup follow-up page if enter wrong code. Needs some design.
* Giving Support what's important not implemented
* Field error not shown on Giving - Travel Money Time

### Sign-up script

1. Visit [https://staging.equalcare.coop/](https://staging.equalcare.coop)
2. Click on Join
3. Enter the code 'HATSTAND'
4. Select a hat
5. Enter a valid postcode in HX7 or OL14
6. If code not valid, will take you to a 'follow up' screen
7. If postcode not valid, will ask you for another
8. If postcode not covered, will take you to 'follow up' screen

I currently suspect there is a defect whereby if you reach the follow-up screen you are unable to restart a join process until your browser session has expired. This needs considering. On the one hand, it's annoying if you enter the code slightly wrong. On the other hand, It would invite repeated attempts and DDoS attacks.

### Change logs

#### UI

Output of `git log --branches=master --oneline v0.20.0..v0.21.0`

```
3cfd183 0.21.0
c770030 chore: revert setting jest roots
af8d044 chore: add validation to travel money time
8a47839 fix: set close target and remove duplicate close
8b1a710 fix: process state for support approaches
06415e4 Merge feature/13-getting-support-with-relationships into master
745fce5 Merge branch 'feature/14-getting-support-with-environment' into 'master'
848f761 chore: revert to testingModuleFactory
6985320 chore: revert to testingModuleFactory
93b4fc3 Merge giving-support-offered routes into master
c07090a feature: add validation code page
300bb12 feature: create giving support offered environment
34813f7 feat: create giving support offered relationships
9d6a31d feature: create giving support offered person
df6bb63 fix: for handling supportApproach on null profile
49785f0 feature: adding follow-up page
8c918c8 feature: update support needs environment
ae85625 fix: incorrectly mapped i18n
af6b7ca Merge i18n/signup into master
50bd9f8 chore: test for complete
ec9ac5c feature: update support needs relationships
26f4685 0.20.1
e0bf06e Merge branch 'feature/12-getting-support-with-person' into 'master'
2a66dd9 fix: handle issues with appraoch rendering
f38024b chore: tidy commented code
a4d2a37 chore: updated test
50a4b56 feature: update support needs person
c6abe07 fix: correct toggle operation if empty profile
5df3b94 chore: implement support needs person
0bb88c0 fix: typo in approaches i18n
b786ab3 Internationalization, further update to the sigup section
51e9412 Internationalization for check-postcode, update
```

#### Graph

Output of `git log --branches=master --oneline v0.24.0..v0.24.2`

```
90b191f 0.24.2
fe761a1 fix: remove incorrect gql mapping to cypher
2840a72 0.24.1
5d78c7f fix: return valid profile if available
```



## 2020-03-02

```
  2020-03-02:
    keycloak:  v0.10.0
    graph_api: v0.24.0
    ui:        v0.20.0
```

### Features:

* Ticket 17 - Getting Support When
* Ticket 16 - Getting Support Approach
* Ticket 184 - Giving Support Approach
* Add internationalisation for account and hello page
* Rough out all giving support sections

### Change log

#### UI Log (v0.19.0 -> v0.20.0)

```
6ebf867 (HEAD -> master, tag: v0.20.0, origin/master) 0.20.0
1ea77e5 chore: fixing husky
938389e test: fix failures in sign-up test
bb2bdef fix: make giving support controller tests pass
c16a79c chore: fix up test for getting support
e9d03eb fix: remove duplicated process step
8c972fa Merge chore/include-all-giving-sections-for-release into master
94ded35 Merge feature/17-getting-support-when into master
1d04609 feature: add support approaches to giving support
a97d3e3 fix: correct some tests
f2301af (feature/16-getting-support-approach) feature: add check for getting support approach
0f950e5 feature: add getting support approaches slider
b04d86c (origin/feature/17-getting-support-when, feature/17-getting-support-when) chore: add in completeness and next step
7bb60d1 Merge branch ‘feature/17-getting-support-when’ of gitlab.com:eccoo-platform/services/user-interface-v1 into feature/17-getting-support-when
a9729f3 feature: getting support profile when
d587988 fix: sequencing issues on proces
03733ae feature: getting support support times
64760c9 (origin/chore/include-all-giving-sections-for-release, chore/include-all-giving-sections-for-release) chore: complete wiring in giving support sections
9b5b4c3 chore: add post for updates (no functionality yet)
5aca273 chore: create support with forms
6763330 chore: include support with sections start
274c1a8 chore: minor tweaks to i18n static config
f9ce974 internationalization of update to i18n/static files
7eb920e internationalization update to create-personal-profile
5d11993 internationization update, amends
ba544a0 internationalization update for account
4386353 Internationalization update for account
55bbdb8 feature: add account namespace to i18n
1e0f82c Merge branch ‘fix/issues-from-latest-merge’ into ‘master’
9cb3cf2 chore: removed unused imports
53a42e8 chore: correct controllers to use new form base
d23f034 fix: mods following code review
195bafe chore: start on all giving sections
02e8a48 chore: one last giving i18n
d1df8f5 chore: complete i18n for giving profile
26198db chore: i18n qualification
38680b8 chore: i18n giving summary
6be9ac4 chore: i18n giving profile
a97fceb chore: tidy getting support snippet
bbab368 fix: location checkbox display
ef6d6be fix: sequencing issues on proces
b47da73 feature: getting support support times
```

#### Graph (v0.23.0 -> v0.24.0)

```
b4117e6 (HEAD -> master, tag: v0.24.0, origin/master) 0.24.0
70c2c11 feature: add fields & mutations to Giving Support
877a0ed chore: fix tests
4d15b30 feature: add getting support needs to profile
f21c70b feature: add support approach updater
```
