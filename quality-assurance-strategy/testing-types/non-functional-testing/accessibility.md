# accessibility

### Aim

To meet WCAG 2.1 AAA

### Accessibility Audit

A full accessibility audit will need to be carried out to see if the site. Example of all the criteria that will need to be assessed:

{% embed url="https://www.accessibilitystatementgenerator.com/" %}

This needs knowledge of accessibility as well as being able to use screen readers efficiently.

### Assistive technology

For the platform to be accessible across [our chosen devices and browsers](https://app.gitbook.com/@equalcare/s/the-platform/quality-assurance-strategy/testing-types/functional-testing/compatibility) by people using the following technology:

* Mouse
* Keyboard 
* Screenreader \(NVDA, Narrator, TalkBack and VoiceOver\)
* Screen magnifier
* Speech recognition
* Switch
* Eyetracker

The current compatibility status of the platform with the devices can be viewed in the [Accessibility testing matrix](https://docs.google.com/spreadsheets/d/1MFj9DnfQN2x-YWWaSMi910DBlae2IDALr8h6krspOuw/edit?usp=sharing)



#### Covered by manual testing 

Keyboard and mouse navigation - can users navigate entire app, accessing all elements using default keys such as tab, shift + tab, enter, space, arrow keys. Ensure that 'skip to content' links consistent throughout the app.

Screen readers - navigate site with monitor off using NVDA, Narrator \(Windows\), VoiceOver \(macOS and iOS\), TalkBack \(Android\) {research screen reader for Linux}

Magnification - Layout and design is still coherent when user has magnified \(research typical maximum magnification level\)

Speech recognition - {needs research}

Switch - all Apple products have built-in switch support. {research Windows and Android}

Eye tracker - {needs research}

Skip links

No flashing content \(if so, is it less than 3 flashes per second?\)

The flow of the HTML is logical for a person using screenreader - screen readers interact with the HTML, not CSS. Is the flow, layout and sequence of content  when viewed as unstyled HTML coherent and sensible?

#### Covered using automated tools

WAVE, pa11y, HTML CodeSniffer \(These were chosen based on the data in this table: [https://alphagov.github.io/accessibility-tool-audit/index.html](https://alphagov.github.io/accessibility-tool-audit/index.html)\)

* Colour contrast
* HTML tree structure
* ARIA labels
* Alt text is present and appropriate
* Links have appropriate descriptions









#### Resources

WCAG 2.1 "quick reference guide" - [https://www.w3.org/WAI/WCAG21/quickref/](https://www.w3.org/WAI/WCAG21/quickref/)

WCAG 2.1 simple checklist - [https://www.thebigtesttheory.com/blog/2019/6/4/wcag-21-accessibility-guidelines-with-test-hints](https://www.thebigtesttheory.com/blog/2019/6/4/wcag-21-accessibility-guidelines-with-test-hints)

What is covered by axe-core - [https://github.com/dequelabs/axe-core/blob/develop/doc/rule-descriptions.md](https://github.com/dequelabs/axe-core/blob/develop/doc/rule-descriptions.md)

HMRC's "How to test for accessibility" - [https://github.com/hmrc/accessibility/blob/master/docs/how-to-test-for-accessibility.md](https://github.com/hmrc/accessibility/blob/master/docs/how-to-test-for-accessibility.md)

Tools recommended by HRMC \(see bottom of page\)- [https://github.com/hmrc/accessibility/blob/master/docs/check-your-services-accessibility-before-you-get-an-audit.md\#make-use-of-automated-helpers](https://github.com/hmrc/accessibility/blob/master/docs/check-your-services-accessibility-before-you-get-an-audit.md#make-use-of-automated-helpers)

