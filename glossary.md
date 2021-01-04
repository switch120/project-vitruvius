# Glossary of Terms

* [Regressions]() - unforseen breakage in an app as a direct result of adjacent modifications. Generally avoided in environments with a proper [CI/CD](#cicd) automated testing setup
* [Release Candidate]() or RC for short - colloquial designation given to the version of an application that most likely represents the final deliverable
* [FOC]() - Front of House
* [BOC]() - Back of House
* [Smoke Testing]() - According to Wikipedia, the term “smoke testing” likely originated in the plumbing industry; plumbers would use smoke to test for leaks and cracks in pipe systems. Some time later, the term was applied to the testing of electronics. Power up a device… if you see smoke, then, well… that’s bad. In the context of Software Engineering, smoke tests are generally a quick glance at the set of changes for verification, as well as any high level [regression](#regressions) checks, before promoting to a clean environment to run a proper QA pass.
* [e2e]() - End to End tests; e.g., simulated environment front->back full user experience automated testing
* [CI/CD]() - Continuous Integration, Continuous Delivery. Nerdspeak for a deployment pipeline that runs automated [e2e](#e2e) tests and is designed to continously deploy as opposed to waiting weeks or months to deploy changes.
