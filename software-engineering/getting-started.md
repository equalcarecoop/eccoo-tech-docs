---
description: >-
  A few notes for a new developer joining the team, may be less useful for a
  more experienced developer.
---

# getting started

## Local Development Environment

As detailed in the previous section:

1. Clone the [Local Dev Env](https://gitlab.com/eccoo-platform/local-dev-env) project from GitLab using Clone with SSH In order to clone with SSH you may need to set up an SSH key on GitLab - [https://docs.gitlab.com/ee/ssh/README.html](https://docs.gitlab.com/ee/ssh/README.html), choosing an ED25519 key. Use `pbcopy < ~/.ssh/id_ed25519.pub` to copy the SSH key to the clipboard from the command line and then paste into GitLab.
2. Follow the instructions in the README to set up your own version of the Equal Care Coop platform

Things to be aware of:  
Once docker is installed, follow these instructions for opening docker engine - [https://stackoverflow.com/a/43365425](https://stackoverflow.com/a/43365425)

As per the local dev env README, you must start the docker containers up in a strict order.

This [section](https://app.gitbook.com/@equalcare/s/platform/~/drafts/-MlUSOMYgNg8UnmvuqW_/software-engineering/frameworks-technologies-and-services) provides useful links to framework documents and getting started documents.

## Useful resources

Alongside the [frameworks, technologies and services](https://app.gitbook.com/@equalcare/s/platform/~/drafts/-MlUSOMYgNg8UnmvuqW_/software-engineering/frameworks-technologies-and-services) links, some useful specific links/resources:

### nunjucks

Useful to render data as a JSON dump in Nunjucks `<pre><code>{{~~~~~ | dump(2)}}</code></pre>` \(~~~~~ = object name\).

### nestjs

Create new nest controller within module

`nest g --flat co <name_of_controller> <name_of_module>`

### GraphQL

[https://www.howtographql.com/basics/0-introduction/](https://www.howtographql.com/basics/0-introduction/)

[http://localhost:3000/graphql](http://localhost:3000/graphql) to run the local Graphql playground

Using a graph db, restful APIs `POST` and `PUT` are both `mutation`.

Check out the mutation syntax and deconstructing of the objects using Graphql playground. [http://localhost:3000/graphql](http://localhost:3000/graphql) Queries written in [Schema Definition Language](https://www.prisma.io/blog/graphql-sdl-schema-definition-language-6755bcb9ce51) - see [GraphQL Core Concepts Tutorial](https://www.howtographql.com/basics/2-core-concepts/) for more information,

\(GraphQL comes with a set of default scalar types out of the box:

* `Int`: A signed 32‐bit integer.
* `Float`: A signed double-precision floating-point value.
* `String`: A UTF‐8 character sequence.
* `Boolean`: true or false.
* `ID`: The ID scalar type represents a unique identifier, often used to refetch an object or as the key for a cache. The ID type is serialized in the same way as a String; however, defining it as an ID signifies that it is not intended to be human‐readable.
* In most GraphQL service implementations, there is also a way to specify custom scalar `Date` type.
* You can define object types and `enums` but these and scalars are the only kinds of types.
* `!` means required, non nullable - Non-Null type modifier.

### Neo4j

[http://localhost:7474/browser/](http://localhost:7474/browser/) to run the local neo4j sandbox.

The neo4j developer advocate youtube videos are very useful. [https://www.youtube.com/c/neo4j/featured](https://www.youtube.com/c/neo4j/featured)

Useful commands in neo4j

`MATCH (u:PlatformUser) return u`

Shows list of all users and can get user id from this.

`MATCH (u:PlatformUser)-[]-(p:Profile) WHERE u.id=‘’ return u, p`

Show user info and profile info for that user.

`MATCH (u:PlatformUser)-[]-(p:Profile:GettingSupport) WHERE u.id=‘’ return u, p`

Show just getting profile info.

`MATCH (u:PlatformUser)-[]-(p:Profile:GettingSupport) WHERE u.id=‘’ DETACH DELETE p`

Delete user profile

[Query \| cypher-query-builder](https://jamesfer.me/cypher-query-builder/classes/query.html#raw)

### CSS

CSS Combinators [CSS Combinators](https://www.w3schools.com/css/css_combinators.asp)

z-index [Understanding CSS z-index - CSS: Cascading Style Sheets \| MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index)

Cubic Beziers [cubic-bezier.com](https://cubic-bezier.com/)

### Git

[How To Set Upstream Branch on Git – devconnected](https://devconnected.com/how-to-set-upstream-branch-on-git/) `git push -u origin <local branch name with no <> >` [How do I delete a local branch in Git? \| Learn Version Control with Git](https://www.git-tower.com/learn/git/faq/delete-local-branch/)

To create a local branch from an upstream branch `git fetch` `git checkout —track origin/<upstream branch name>`

`git describe` to see what version currently have locally

`git stash pop` to pull back stashed changes

[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) and

[angular/CONTRIBUTING.md at master · angular/angular · GitHub](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#type) for naming types

[How to Rename Git Local and Remote Branches](https://www.w3docs.com/snippets/git/how-to-rename-git-local-and-remote-branches.html) `git branch -m <old-name> <new-name>`

[What is Your Branching Model?](https://paulhammant.com/2013/12/04/what_is_your_branching_model/)

[https://martinfowler.com/bliki/FeatureToggle.html](https://martinfowler.com/bliki/FeatureToggle.html)

[A Visual Git Reference](http://marklodato.github.io/visual-git-guide/index-en.html)

[Home // Think Like \(a\) Git](http://think-like-a-git.net/)

Use `git pull --rebase` whenever pulling which will place any changes you’ve made after the updates in the main repo. [https://stackoverflow.com/questions/18930527/difference-between-git-pull-and-git-pull-rebase](https://stackoverflow.com/questions/18930527/difference-between-git-pull-and-git-pull-rebase)

[The Ultimate Guide to Git Merge and Git Rebase](https://www.freecodecamp.org/news/the-ultimate-guide-to-git-merge-and-git-rebase/)

[https://opensource.com/article/18/6/git-reset-revert-rebase-commands](https://opensource.com/article/18/6/git-reset-revert-rebase-commands)

`npm version` [npm-version \| npm Docs](https://docs.npmjs.com/cli/v7/commands/npm-version)

`npm version patch -m “Upgrade to %s for reasons”` `git push —tags origin master`

### CQRS

Command Query Responsibility Segregation

[CQRS](https://martinfowler.com/bliki/CQRS.html)

A pattern, contrast with CRUD.

[CQRS, Task Based UIs, Event Sourcing agh! \| Greg Young](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)

Events handling

[CQRS: What? Why? How?. CQRS is a useful pattern to reason… \| by Stéphane Derosiaux \| Medium](https://sderosiaux.medium.com/cqrs-what-why-how-945543482313)

[CQRS Explained With Nest JS. We will be developing a simple CQRS app… \| by Renjith P \| The Startup \| Medium](https://medium.com/swlh/cqrs-explained-with-nest-js-1bcf83c5c839)

### Accessibility

[WebAIM: Keyboard Accessibility](https://webaim.org/techniques/keyboard/)

[Labeling Controls • Forms • WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/forms/labels/)

[Timing Guidelines for Exposing Hidden Content](https://www.nngroup.com/articles/timing-exposing-content/)

[Quick tip: Never remove CSS outlines - The A11Y Project](https://www.a11yproject.com/posts/2013-01-25-never-remove-css-outlines/)

[Slide 109 – List of links – Empathy in Accessibility](https://empathy-in-accessibility.netlify.app/slides/109.html)

[Forms in HTML documents](https://www.w3.org/TR/html4/interact/forms.html#edef-FIELDSET)

[ARIA: button role - Accessibility \| MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role)

[WAI-ARIA: Role=Tooltip • Digital A11Y](https://www.digitala11y.com/tooltip-role/)

[Using the presentation role - Accessibility \| MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_presentation_role#aria_attributes_used)

[What the Heck is ARIA? A Beginner’s Guide to ARIA for Accessibility \| Lullabot](https://www.lullabot.com/articles/what-heck-aria-beginners-guide-aria-accessibility)

[hidden - HTML: HyperText Markup Language \| MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/hidden)

[Building Accessible Menu Systems — Smashing Magazine](https://www.smashingmagazine.com/2017/11/building-accessible-menu-systems/)

[Accessible hiding and aria-hidden example - Orange digital accessibility guidelines](https://a11y-guidelines.orange.com/en/web/components-examples/accessible-hiding/)

[Three CSS Alternatives to JavaScript Navigation \| CSS-Tricks](https://css-tricks.com/three-css-alternatives-to-javascript-navigation/)

[WAI-ARIA: aria-haspopup \(Property\) • Digital A11Y](https://www.digitala11y.com/aria-haspopup-properties/)

[Alternatives of hamburger menu. When it comes to controversial UI, the… \| by CanvasFlip \| UX Planet](https://uxplanet.org/alternatives-of-hamburger-menu-a8b0459bf994)

[Online Referral Form \| Vision Australia. Blindness and low vision services](https://visionaustralia.org/referral/medical-professionals/form#)

[AccessibilityOz](https://www.accessibilityoz.com/)

[Solved with CSS! Dropdown Menus \| CSS-Tricks](https://css-tricks.com/solved-with-css-dropdown-menus/)

[https://a11ysupport.io/](https://a11ysupport.io/)

[https://nolanlawson.com/2019/11/05/what-ive-learned-about-accessibility-in-spas/](https://nolanlawson.com/2019/11/05/what-ive-learned-about-accessibility-in-spas/)

### Testing

Useful testing commands:

`npm run test — <filename>` to run single test

`npm run test:cov — <filename>` to get coverage

`open ./coverage/lcov-report/sign-up.controller.ts.html` to open coverage in browser

### GDS - GOV Design System

[Patterns – GOV.UK Design System](https://design-system.service.gov.uk/patterns/)





