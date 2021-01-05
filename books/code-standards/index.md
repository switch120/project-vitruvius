# Code Standards and Best Practices

### Table of Contents
* [Version Control](#version-control)
* [Linting](#linting)
  * [Javascript / Typescript](#javascript-typescript-linting)
* [Language Specific Standards](#language-specific-standards)
  * [C-Syntax Languages](#c-syntax)
* [Framework Specific Standards](#framework-specific-standards)
  * [Angular](#angular)
  * [React](#react)
  * [Vue](#vue)
  * [Laravel](#laravel)
  * [Kentico](#laravel)

## Version Control

<section align="right">
  <img src="../../images/pirates_code.jpg" style="width: 75px" />
  <h2 style="text-align: center; margin-top: -8px">9</h2>
</section>

## [Github](../devops#github)
Github is the preferred version control service whenever possible.

### Broad Policies
* [Pull Requests](../devops#pull-requests) are always reviewed by a second party before merging
* Multi-factor Auth (MFA) enabled
* No direct edits, _ever_ to a `master*` branch
* Avoid rebasing wherever possible
* No private account keys _ever_
* **Always** triple check `.gitignore` for sensitive files

<div style="clear: both;"></div>

### New / Acquired Project Setup
* Set to Private
* (New) Initialized w/ Readme
* Assigned new or existing [Github Team](../devops#github-teams) with Read/Write access
* `master*` branch locked from direct commits. 
> Note: **Include Administrators**.
* Create `master-dev` branch from `master`

### Development Lifecycle
* New dev / feature branches are created from `master-dev`
* During development, frequently `pull from origin/master-dev` to keep the working branch up to date with any changes being merged in parallel
* Local work is [tested](../devops#testing), [linted](../devops#linting), committed, and pushed to remote
> Note: Please ensure a full Prod build succeeds before committing code. Self-onus on this prevents long waits for pre-push builds locally.
* [Pull Request](../devops#pull-requests) submitted against `master-dev` and assigned reviewer
* **Any oustanding merge conflicts** should be resolved when the PR is submitted, _not_ by the reviewer. Frequently pulling from `master-dev` and resolving locally will ease this aggravation.
* Merges are accumulated in `master-dev` and [smoke tested](../../glossary#smoke-testing) by the _active_ dev team and any QA team members that may happen to be paying attention. It is **expected** that the [Dev environment](../devops#dev-environments) could be dirty at any time so no concerted QA efforts should ever be mounted there.
* Once sanity/smoke tests have passed, `master-dev` is **promoted** to `master-qa` and deployed
* When QA is deployed, *patch* version is updated: `0.1.1` -> `0.1.2`. Minor/major patch versions can be upreved at appropriate times.
> Note: For smaller projects this promotion could go straight to `master` if no in-earnest QA/Test environment is available. Consider the following as optional depending on the size and needs of the current project
* After a thorough QA pass, `master-qa` is promoted to `master-stage` and deployed. At this point the number of deployments should be _considerably_ less than QA and the release is considered to be a [Release Candidate (RC)](../../glossary#release-candidate) with zero showstopping bugs and _very_ minimal edge case bugs
* Once all QA tests have passed and client has signed off on offical release, `master-stage` is promoted to `master` and a new release version is cut from `master` with any relevant release notes
---

## Linting

<section style="float: right; clear: both;">
  <img src="../../images/pirates_code.jpg" style="width: 75px" />
  <h2 style="text-align: center; margin-top: -8px">7</h2>
</section>

Whenever possible all projects should be properly linted. Each language / framework is going to present different challenges for achieving this, but at the very least [Green Field Projects](../architecture#green-field-projects) should institute the linter of choice for the situation. Below are some examples of baseline Linter configurations.

<div style="clear: both;"></div>

### Javascript / Typescript Linting
### [esLint](https://eslint.org/)
Sample `.eslintrc` file: [.eslintrc](./eslintrc.md)

---

## Language Specific Standards

<section style="float: right; clear: both;">
  <img src="../../images/pirates_code.jpg" style="width: 75px" />
  <h2 style="text-align: center; margin-top: -8px">9</h2>
</section>

### C-Syntax
* Preferred editor: Visual Studio Code
* Default Code formatter
* Preferred casing
  * Classes: Pascal
  * Variables: Camel
* Do _not_:
  * Use brackets for single-line conditional: `if (true) { return true; }`
  * _Always_ Linebreak for every `.accessor` (break within reason)
  * Use indescript variable names, e.g., `x`, `something`

### HTML
* VSC: Disable default wrap, set to 0
* Do _not_: 
  * Put each attribute on separate line (exception: JSX / React)
  * Put closing tag of empty element on new line

<div style="clear: both;"></div>

---

## Framework Specific Standards
### Angular
### React
### Vue
### Laravel
### Kentico