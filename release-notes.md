# release notes

## 

## 2021-03-12-1

```text
  2020-03-12-1:
    keycloak:  v0.10.0
    graph_api: v0.25.1
    ui:        v0.24.2  
```

### Features and fixes





### Change log for ui-v1 since v0.24.0

```text
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

```text
832951b 0.25.1
0cc94d5 fix: non-nullable preferences array cypher
```



## 2021-03-11

```text
  2020-03-11:
    keycloak:  v0.10.0
    graph_api: v0.25.1
    ui:        v0.24.0
```

### Features and fixes

* Various fixes including error validation

### Change log for ui-v1 since v0.23.0

```text
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

```text
832951b 0.25.1
0cc94d5 fix: non-nullable preferences array cypher
```

## 2021-03-04

```text
  2020-03-04:
    keycloak:  v0.10.0
    graph_api: v0.25.1
    ui:        v0.22.0
```

### Features

* Error page \(custom for 404, with a default 'something went wrong'\)
* Background blobs
* Complete Giving Support edit pages \(preferences and what's on\)
* Added modal template to more Giving Support edit pages

### Fixes

* Many minor fixes

### Known issues / omissions:

* URLs still to be remapped in `/profile/giving-support` edit screens. In fact, quite a lot of tech debt here
* Should hide stack-trace in error page for production environments
* No error fields on giving Travel Money Time

### Change logs

#### ui-v1 since v0.21.0

```text
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

```text
832951b 0.25.1
0cc94d5 fix: non-nullable preferences array cypher
```

#### Change log for graph-api since v0.24.0

```text
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

```text
  2020-03-03:
    keycloak:  v0.10.0
    graph_api: v0.24.2
    ui:        v0.21.0
```

### Major Changes

* Added Person / Relationships / Environment forms for both Giving and Getting support
* Added invitation code and follow-up screens for sign-up \(both need reviewing\). Refactored the sign-up process to enforce valid code and covered postcode. \(It was previously possible to leap steps in the process. No longer!\)
* Added field-level validation to Giving Support Travel Money Time page

### Minor fixes:

* Fixed issue of null profile returned from graph in valid Giving / Getting Support query.
* Fixes to issues around supportApproaches

### Known issues / omissions:

* Potential issue with getting stuck on signup follow-up page if enter wrong code. Needs some design.
* Giving Support what's important not implemented
* Field error not shown on Giving - Travel Money Time

### Sign-up script

1. Visit [https://staging.equalcare.coop/](https://staging.equalcare.coop/)
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

```text
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

```text
90b191f 0.24.2
fe761a1 fix: remove incorrect gql mapping to cypher
2840a72 0.24.1
5d78c7f fix: return valid profile if available
```



## 2020-03-02

```text
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

#### UI Log \(v0.19.0 -&gt; v0.20.0\)

```text
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

#### Graph \(v0.23.0 -&gt; v0.24.0\)

```text
b4117e6 (HEAD -> master, tag: v0.24.0, origin/master) 0.24.0
70c2c11 feature: add fields & mutations to Giving Support
877a0ed chore: fix tests
4d15b30 feature: add getting support needs to profile
f21c70b feature: add support approach updater
```

