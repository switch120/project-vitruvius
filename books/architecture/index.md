# Architecture

### Table of Contents
* [Project DevOps Preferences](#project-devops-preferences)
  * [Centralized Deployment](#centralized-deployment)
  * [Linting] (#linting)
* [Green Field Project Preferences](#greenfield)
  * [Platform Agnostic](./platform-agnostic)
  * Microsoft / .NET
  * OSS
* [Cloud Platform Preferences](#cloud)
  * [AWS](#aws)
  * [GCP](#gcp)
  * [Azure](#azure)
  * [FireBase](#firebase)


## Project DevOps Preferences
<div align="center">
  <img src="../../images/pirates_code.jpg" width="100" />
  <br />
  <strong>7</strong>
</div>

### Centralized Deployment
If at all possible any project, acquired or especially new, a centralized deployment pattern should be implemented.
#### Why?
So any team member, or even potentially the client, can deploy. This ensures we can meet any continuous delivery requirement while not bottlenecking team members.
#### How?
Generally with [Jenkins](../devops/index.md#jenkins). If or another [CI/CD](../../glossary.md#cicd) service is not available, alternatives such as [Heroku, Github pages, FourSquare, etc.](../cloud-platforms/index.md) should be explored.

### Linting
Whenever possible a [Linter](../devops/index.md#linting) should be configured with any *new project*. Existing projects may already have too much [Technical Debt](../../glossary.md#technical-debt) to reasonably integrate a linter, but best efforts should be made as it can help identify issues early on and prevent human error from reading poorly formatted code. See [Code Standards](../code-standards/#linting) for specific Linting recommendations.

Linters should always be *connected to commit actions*. Easiest way in OSS is using [Husky](https://www.npmjs.com/package/husky) to add a `pre-commit` linter hook.
> TODO: .NET consideration for pre-commit linting?

## Green Field Project Preferences
A project from-scratch provides a lot more flexibilty to establish a stable foundation to build on, allowing the team to leverage things like [unit testing](../code-standards/index.md#unit-tests) and [linting](../devops/index.md#linting) integration early on. Best efforts should be made to get _at least_ the scaffolding for these services set up so it's a little closer to turn-key if it's ever needed. Waiting to add these things later adds considerable technical debt right up front.

### Platform Agnostic
<div align="center">
  <img src="../../images/pirates_code.jpg" width="100" />
  <br />
  <strong>9</strong>
</div>
Regardless of platform there are some basics that should be considered for all green field projects

* Setup [Centralized Deployment](#centralized-deployment)
* [Virtualize whenever possible](../devops/index.md#development-environments)
* [Configure a Linter](#linting)
* [SCSS for styles](../code-standards/index.md#css)

### Microsoft / .NET
> TBD

### OSS
<div align="center">
  <img src="../../images/pirates_code.jpg" width="100" />
  <br />
  <strong>8</strong>
</div>

* Frontend
  * Angular / Typescript
  * Husky
* Backend
  * NestJS / TypeOrm
  * PassportJS
  * Husky
* Platform
  * AWS
  * MySql / Aurora (RDS)
  * Containerized (ECS)
  * Load Balanced
* Deployment
  * Jenkins
  * CloudFront for static assets
  * Containerized Deployment for backend

## Cloud Platform Preferences
### AWS
### GCP
### Azure
### FireBase