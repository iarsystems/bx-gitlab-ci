<img align="right" src="https://avatars.githubusercontent.com/u/22105643?s=96&v=4" />


# IAR Build Tools for Arm on GitLab with Linux runners


>[!WARNING]
>The information in this repository is subject to change without notice and does not constitute a commitment by IAR. While it serves as a valuable reference for DevOps Engineers implementing Continuous Integration with IAR Tools, IAR assumes no responsibility for any errors, omissions, or specific implementations.


## Introduction
From a CI/CD perspective, the [IAR Build Tools for Arm](https://iar.com/bxarm) comes with everything you need to build embedded firmware projects from the command line. This tutorial provides a simple example with general guidelines on how to set up a CI/CD pipeline using [GitLab CI](https://gitlab.com) while taking advantage of the so-called __[GitLab self-managed runners][gl-smr-url]__.

In case you need an introduction on how to get started with GitLab, use their [Tutorials](https://docs.gitlab.com/?tab=Tutorials).


## Prerequisites
Before you begin, you will need to download and install the following:
- IAR Build Tools for Arm 9.60.2 for Ubuntu 22.04 x64 ([`bxarm-9.60.2.deb`](https://updates.iar.com/?product=BXARM&version=9.60))
   - IAR customers can download it directly from [IAR MyPages](https://iar.my.site.com/mypages). If you do not have a license, [contact IAR Sales](https://iar.com/about/contact).

You also will need:
- A GitLab [organization account][gl-join-url]
   - or a GitLab [enterprise account][gl-join-url].

>[!NOTE]
>This guide was based on the options available in GitLab v17.4.

## Quickstart
Under your organization's GitLab account:

- Go to [Create New... → Import Project → Repository by URL](https://gitlab.com/projects/new#import_project).
- Fill __Git repository URL__ with this repository's URL.
- In the __Project URL__, `Pick a group or namespace`.
- Make sure the __Visibility level__ is set to 🔘 **Private**.
- Finally click `   Create project   `.

Once the importing process is complete, a banner will show up with the message `The project was successfully imported.` and you will be taken to your imported repository.


## A GitLab workflow example
On your private repository, navigate to the [`.gitlab-ci.yml`](.gitlab-ci.yml) workflow file. This file uses the [GitLab-flavored YAML](https://docs.gitlab.com/ee/ci/quick_start/#create-a-gitlab-ciyml-file) to describe a workflow containing multiple jobs typically used in embedded firmware projects.

Refer to the [`.gitlab-ci.yml`](.gitlab-ci.yml) workflow file for detailed comments.

## Adding runners to your repository
It is straightforward to set up a self-managed GitLab runner in a Linux host with the IAR Build Tools for Arm for building your project on automated workflows:
- Navigate to your repository's __Settings__ → __CI/CD__ (`https://gitlab.com/<username>/bx-gitlab-ci/-/settings/ci_cd`).
- `  Expand  ` __Runners__.
- Disable - [  ] __Instance Runners__.
- In __Project Runners__, click `  New project runner  `.
- Create a new __Tag__ for your runner. (e.g., `self-hosted`).
- Click `  Create runner  `.

### Registering a GitLab Runner
You will be taken to the next page for registering a newly created runner.
- Select __`🔘 Linux`__ as the __Operating System__.
- This page also provides a link ("How do I install GitLab Runner?"). Install the GitLab Runner on the same host where you already have the IAR Build Tools for Arm pre-installed.
- Follow the remaining steps provided on the __Register runner__ page.
- When asked for __Entering an executor__, type `shell`.
- Once "🎉 You've registered a new runner!", click `  View runners  `.

![image](https://github.com/user-attachments/assets/43738619-9d55-4151-89b4-9cda3081a225)


You can have as many parallel build nodes with runners as your license allows you to. [Contact IAR Sales](https://iar.com/about/contact) for expanding your build capacity.


## Summary
This tutorial provided an overview of how to get started with the IAR Build Tools for Arm on GitLab using Linux self-managed runners. Development teams can immediately benefit from the comprehensive feedback these modern workflows offer, enabling them to quickly build, analyze, test, and deploy with high quality.

[__` Follow us `__](https://github.com/iarsystems) on GitHub to get updates about tutorials like this and more.


## Issues
For technical support contact [IAR Customer Support][url-iar-customer-support].

For questions or suggestions related to this tutorial: try the [wiki][url-repo-wiki] or check [earlier issues][url-repo-issue-old]. If those don't help, create a [new issue][url-repo-issue-new] with detailed information.


<!-- links -->
[url-iar-customer-support]: https://iar.my.site.com/mypages/s/contactsupport

[iar-bxarm-url]: https://www.iar.com/bxarm

[gh-iar-url]: https://github.com/IARSystems
    
[gl-doc-yaml-url]: https://docs.gitlab.com/ee/ci/yaml/gitlab_ci_yaml.html
[gl-smr-url]: https://docs.gitlab.com/runner
[gl-join-url]: https://gitlab.com/users/sign_in
[gl-pipeline-url]: https://docs.gitlab.com/ee/ci/pipelines

[url-repo]: https://github.com/IARSystems/bx-gitlab-ci
[url-repo-wiki]: https://github.com/IARSystems/bx-gitlab-ci/wiki
[url-repo-issue-new]: https://github.com/IARSystems/bx-gitlab-ci/issues/new
[url-repo-issue-old]: https://github.com/IARSystems/bx-gitlab-ci/issues?q=is%3Aissue+is%3Aopen%7Cclosed
