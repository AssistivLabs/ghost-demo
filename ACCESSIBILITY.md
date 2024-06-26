# Accessibility @ Ghost

For **help**, **support**, **questions** and **ideas** please use **[our forum](https://forum.ghost.org)**  🚑.

---

## Strategy

We want everyone to be equally able to use Ghost. To that end, we follow a multi-pronged strategy to ensure the platform is as accessible as possible for people using assistive technologies, neurodivergent people, and people with other conditions such as color vision deficiencies, repetitive strain injuries, and other [permanent, temporary, or situational disabilities](https://digital.gov/resources/advanced-accessibility/#becoming-literate-in-accessibility-2).

Our accessiblity strategy incorporates the components listed below to varying degrees. We regularly complete self-reviews of our [accessiblity maturity](https://www.w3.org/TR/maturity-model/) to better understand the state of each of the following:

* [Internal education](#internal-education)
* [Shifting left into design process/tools](#shifting-left-into-design-processtools)
	* [Community usability testing](#community-usability-testing)
	* [Manual validation](#manual-validation)
* [Accessibility as part of our “definition of done” in the SDLC](#accessibility-as-part-of-our-definition-of-done-in-the-sdlc)
	* [Linters to catch developer accessibility mistakes when coding](#linters-to-catch-developer-accessibility-mistakes-when-coding)
	* [axe-core in CI](#axe-core-in-ci)
	* [End-to-end coverage](#end-to-end-coverage)
* [External audits](#external-audits)

## Internal education

There is a ton of great information and trainings available for Ghost contributors who are motivated to learn more about how to create inclusive user interfaces. Some of our favorites include the following:

* Marcy Sutton’s [Testing Accessibility](https://testingaccessibility.com/)
* Sara Soueidan’s [Practical Accessibility](https://practical-accessibility.today/)
* [Digital Accessibility Foundations Free Online Course](https://www.w3.org/WAI/courses/foundations-course/) offered by the W3C’s Web Accessibility Initiative

We also have a [dedicated accessibility topic in our community forum](https://forum.ghost.org). That’s the best place to start for accessibility questions specific to the Ghost platform.

## Shifting left into design process/tools

> Nothing about us without us.

Whenever possible, we involve disabled people in the process of designing major features of the Ghost platform. We are fortunate to have a community of people with disabilities who contribute feedback in the UX research and design phases of our process.

If you’re embarking on a major new feature for Ghost, you can use this form to [request a design review by our disabled community](https://ghost.org/form).

### Community usability testing

For major UI changes, we tap our community to do usability testing on the following assistive technologies and tools:

* Screen readers:
	* NVDA on Windows
	* TalkBack on Android
	* VoiceOver on macOS
	* VoiceOver on iOS
* Voice control:
	* Voice Control on macOS
	* Dragon Naturally Speaking on Windows

We can always use more volunteers to help with usability testing! Use this form to [add your name to the pool](https://ghost.org/form).

### Manual validation

We highly encourage [contributors](https://github.com/TryGhost/Ghost/blob/main/.github/CONTRIBUTING.md) to attempt to manually validate that UI changes maintain or improve the accessibility of Ghost.

The following are some tools we recommend for checking your work:

* Test on screen readers using [Assistiv Labs](https://assistivlabs.com) – use this form to [request access](https://ghost.org/form) and see these [getting started videos](https://assistivlabs.com/support/getting-started) for help getting oriented to the platform
* [Microsoft Accessibility Insights](https://accessibilityinsights.io/)
* [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
* [Adobe Color Contrast Analyzer](https://color.adobe.com/create/color-contrast-analyzer)

By taking advantage of the resources listed above, you will help us by reducing the number of issues raised by the yearly [external audits](#external-audits) we commission.

## Accessibility as part of our “definition of done” in the SDLC

As we say in our [contributors guide](https://github.com/TryGhost/Ghost/blob/main/.github/CONTRIBUTING.md), we aim to merge any straightforward, well-understood bug fixes or improvements immediately, as long as they pass our tests (run `yarn test` to check locally).

These tests include both static analysis using axe-core and end-to-end accessibility regression testing using Assistiv Labs. All tests must pass before you can merge your work.

The following will help you avoid any surprises when it comes time to submit your PR!

### Linters to catch developer accessibility mistakes when coding

Most modern IDEs allow you to add a linter that will catch a certain class of accessibility bug as you’re writing your code. We won’t list them all, but an example is the [axe Accessibility Linter for Visual Studio](https://marketplace.visualstudio.com/items?itemName=deque-systems.vscode-axe-linter).

We include [axe-core](https://github.com/dequelabs/axe-core) in our repo and you can scan for issues at any time by running `yarn:lint`.

### axe-core in CI

Our GitHub Actions workflow runs [axe-core](https://github.com/dequelabs/axe-core) as a pre-merge check. Changes that include accessibility defects will be automatically blocked from merging.

### End-to-end coverage

In addition to axe-core, our GitHub Actions workflow runs [Assistiv Labs end-to-end tests](https://assistivlabs.com/use-cases/end-to-end-accessibility-testing) across our critical user flows. Changes that result in new failures will be automatically blocked from merging.

## External audits

All of the preceding guidance is in service of end-users, ultimately, but our best proof that we’re doing the right thing by them is how our work performs in external audits.

On approximately a yearly cadence, the Ghost Foundation contracts with [Zenyth](https://www.zenythgroup.com) to provide comprehensive accessibility audits of our platform.

Professional auditors at Zenyth review both workflows (e.g., newsletter subscription) and common elements (e.g., the website footer) against  [WCAG 2.2](https://www.w3.org/TR/WCAG22/) A and AA and provide Accessibility Conformance Reports (ACRs) for both the authoring platform and the subscriber-facing website.

Review past ACRs:

* [2023](https://ghost.org/accessibility/acr/2023)
* [2022](https://ghost.org/accessibility/acr/2022)
* [2021](https://ghost.org/accessibility/acr/2021)
