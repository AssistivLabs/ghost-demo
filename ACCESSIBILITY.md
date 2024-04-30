# Accessibility @ Ghost

For **help**, **support**, **questions** and **ideas** please use **[our forum](https://forum.ghost.org)**  🚑.

---

## Strategy

We want everyone to be equally able to use Ghost. To that end, we follow a multi-pronged strategy to ensure the platform is as accessible as possible for people using assistive technologies, neurodivergent people, and people with other conditions such as color vision deficiencies, repetitive strain injuries, and other [permanent, temporary, or situational disabilities](https://digital.gov/resources/advanced-accessibility/#becoming-literate-in-accessibility-2).

Our accessiblity strategy incorporates the components listed below to varying degrees. We regularly complete self-reviews of our [accessiblity maturity](https://www.w3.org/TR/maturity-model/) to better understand the state of each of the following:

* Internal education
* Shifting left into design process/tools
* Usability testing
* Manual auditing
* Accessibility as part of our “definition of done” in the SDLC
	* Linters to catch developer accessibility mistakes when coding
	* axe-core in CI
	* End-to-end coverage

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

## Usability testing

For major UI changes, we tap our community to do usability testing on the following assistive technologies and tools:

* Screen readers:
	* NVDA on Windows – use this form to [request access to our Assistiv Labs account](https://ghost.org/form)
	* TalkBack on Android
	* VoiceOver on macOS
	* VoiceOver on iOS
* Voice control:
	* Voice Control on macOS
	* Dragon Naturally Speaking on Windows

We can always use more volunteers to help with usability testing! Use this form to [add your name to the pool](https://ghost.org/form).

## Manual auditing

We highly encourage [contributors](https://github.com/TryGhost/Ghost/blob/main/.github/CONTRIBUTING.md) to attempt to manually validate that UI changes maintain or improve the accessibility of Ghost.

The following are some tools we recommend for checking your work:

* [Microsoft Accessibility Insights](https://accessibilityinsights.io/)
* [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
* [Adobe Color Contrast Analyzer](https://color.adobe.com/create/color-contrast-analyzer)

## Accessibility as part of our “definition of done” in the SDLC

As we say in our [contributors guide](https://github.com/TryGhost/Ghost/blob/main/.github/CONTRIBUTING.md), we aim to merge any straightforward, well-understood bug fixes or improvements immediately, as long as they pass our tests (run `yarn test` to check locally).

These tests include both static analysis using axe-core and end-to-end accessibility regression testing using Assistiv Labs. All tests must pass before you can merge your work.

The following will help you avoid any surprises when it comes time to submit your PR!

### Linters to catch developer accessibility mistakes when coding

Most modern IDEs allow you to add a linter that will catch a certain class of accessibility bug as you’re writing your code. We won’t list them all, but an example is the [axe Accessibility Linter for Visual Studio](https://marketplace.visualstudio.com/items?itemName=deque-systems.vscode-axe-linter).

### axe-core in CI

Our GitHub Actions workflow runs [axe-core](https://github.com/dequelabs/axe-core) as a pre-merge check. Changes that include accessibility defects will be automatically blocked from merging.

### End-to-end coverage

In addition to axe-core, our GitHub Actions workflow runs [Assistiv Labs end-to-end tests](https://assistivlabs.com/use-cases/end-to-end-accessibility-testing) across our critical user flows. Changes that result in new failures will be automatically blocked from merging.
