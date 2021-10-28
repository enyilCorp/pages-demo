---
#
# Editable - Title and Description display on the page and in HTML meta tags
#
title: GitHub Actions and CircleCI tool comparison
description: You can find a range of tools to support the CI/CD process. GitHub Actions and CircleCI share several similarities in configuration, which makes migration to GitHub Actions relatively straightforward.
#
# Don't edit items below - they control the page layout
#
return-top: yes
layout: page
page-type: subpage
page-description: yes
permalink: /guides/tools/actions-v-circleci
#
---
## GitHub Actions and CircleCI tool comparison

CircleCI and GitHub Actions both allow you to create workflows that automatically build, test, publish, release, and deploy code. CircleCI and GitHub Actions share some similarities in workflow configuration:

- Workflow configuration files are written in YAML and stored in the repository.
- Workflows include one or more jobs.
- Jobs include one or more steps or individual commands.
- Both CircleCI and GitHub Actions support running steps inside of a Docker image.
- CircleCI and GitHub Actions support setting environment variables in the configuration file.
- Steps or tasks can be reused and shared with the community. Both CircleCI and GitHub Actions provide a mechanism to reuse and share tasks in a workflow. CircleCI uses a concept called orbs, written in YAML, to provide tasks that people can reuse in a workflow.

### Some key differences between GitHub Actions and CircleCI

- CircleCI’s automatic test parallelism automatically groups tests according to user-specified rules or historical timing information. This functionality is not built into GitHub Actions.
- Actions that execute in Docker containers are sensitive to permissions problems since containers have a different mapping of users.
  - You can avoid many of these problems by not using the `USER` instruction in your _Dockerfile_.
  - CircleCI provides a set of pre-built images with common dependencies. These images have the `USER` set to `circleci`, which causes permissions to conflict with GitHub Actions.
  - We recommend that you move away from CircleCI's pre-built images if you migrate to GitHub Actions. In many cases, you can use actions to install the additional dependencies you need.

### Migrating workflows and jobs

CircleCI defines `workflows` in the _config.yml_ file, which allows you to configure more than one workflow. GitHub requires one workflow file per workflow, and as a consequence, does not require you to declare `workflows`. You'll need to create a new workflow file for each workflow configured in config.yml.

Both CircleCI and GitHub Actions configure `jobs` in the configuration file using similar syntax. If you configure any dependencies between jobs using `requires` in your CircleCI workflow, you can use the equivalent GitHub Actions `needs` syntax.

### Migrating orbs to actions

Both CircleCI and GitHub Actions provide a mechanism to reuse and share tasks in a workflow. CircleCI uses a concept called orbs, written in YAML, to provide tasks that people can reuse in a workflow. GitHub Actions has powerful and flexible reusable components called actions, which you build with either JavaScript files or Docker images.

You can create actions by writing custom code that interacts with your repository in any way you'd like, including integrating with GitHub's APIs and any publicly available third-party API. For example, an action can publish npm modules, send SMS alerts when urgent issues are created, or deploy production-ready code.

CircleCI can reuse pieces of workflows with YAML anchors and aliases. GitHub Actions supports the most common need for reusability using build matrixes.

### More information

[Migrating from CircleCI to GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/migrating-from-circleci-to-github-actions)

[Core Concepts for GitHub Actions](https://docs.github.com/en/actions/getting-started-with-github-actions/core-concepts-for-github-actions)

[CircleCI integration with GitHub](https://circleci.com/integrations/github/)

[CircleCI Documentation](https://circleci.com/docs/)

---

[Return to Guides]({{ site.baseurl }}/guides)
