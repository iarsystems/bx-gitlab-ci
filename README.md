<img align="right" src="https://avatars.githubusercontent.com/u/22105643?s=96&v=4" />


# IAR Build Tools for Arm on GitLab CI/CD


>[!WARNING]
>The information in this repository is subject to change without notice and does not constitute a commitment by IAR. While it serves as reference model for implementing Continuous Integration with IAR Tools, IAR assumes no responsibility for any errors, omissions, or specific implementations.


## Introduction
From a CI/CD perspective, the [IAR Build Tools for Arm](https://iar.com/cx) comes with everything you need to build embedded firmware projects from the command line. This example provides a simple example with general guidelines on how to set up a CI/CD pipeline using [GitLab CI](https://gitlab.com).

In case you need an introduction on how to get started with GitLab, use their [examples](https://docs.gitlab.com/?tab=examples).


## Prerequisites
Before you begin, you will need:
- A CI Token for the IAR Build Tools[^1].
- A [GitLab account][gl-join-url]

## Quickstart
Under your GitLab account:

- Go to [Create New... → Import Project → Repository by URL](https://gitlab.com/projects/new#import_project).
- Fill __Git repository URL__ with this repository's URL.
- In the __Project URL__, `Pick a group or namespace`.
- Make sure the __Visibility level__ is set to 🔘 **Private**.
- Finally click `   Create project   `.

Once the importing process is complete, a banner will show up with the message `The project was successfully imported.` and you will be taken to your imported repository.


## A GitLab workflow example
On your repository, navigate to the [`.gitlab-ci.yml`](.gitlab-ci.yml) workflow file. This file uses the [GitLab-flavored YAML](https://docs.gitlab.com/ee/ci/quick_start/#create-a-gitlab-ciyml-file) to describe a workflow containing multiple jobs typically used in embedded firmware projects.

Refer to the [`.gitlab-ci.yml`](.gitlab-ci.yml) workflow file for detailed comments.

## Summary
This example provided an overview of how to get started with the IAR Build Tools for Arm on GitLab CI/CD. Development teams can immediately benefit from the comprehensive feedback these modern workflows offer, enabling them to quickly build, analyze, test, and deploy with high quality.

[__` Follow us `__](https://github.com/iarsystems) on GitHub to get updates about examples like this and more.


## Issues
For technical support contact [IAR Customer Support][url-iar-customer-support].

For questions or suggestions related to this example: try the [wiki][url-repo-wiki] or check [earlier issues][url-repo-issue-old]. If those don't help, create a [new issue][url-repo-issue-new] with detailed information.


<!-- links -->
[url-iar-customer-support]: https://iar.my.site.com/mypages/s/contactsupport

[iar-cxarm-url]: https://www.iar.com/cx

[gh-iar-url]: https://github.com/iarsystems
    
[gl-doc-yaml-url]: https://docs.gitlab.com/ee/ci/yaml/gitlab_ci_yaml.html
[gl-join-url]: https://gitlab.com/users/sign_in
[gl-pipeline-url]: https://docs.gitlab.com/ee/ci/pipelines

[url-repo]: https://github.com/iarsystems/gitlab-ci-example
[url-repo-wiki]: https://github.com/iarsystems/gitlab-ci-example/wiki
[url-repo-issue-new]: https://github.com/iarsystems/gitlab-ci-example/issues/new
[url-repo-issue-old]: https://github.com/iarsystems/gitlab-ci-example/issues?q=is%3Aissue+is%3Aopen%7Cclosed
