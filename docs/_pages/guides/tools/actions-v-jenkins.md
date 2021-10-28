---
#
# Editable - Title and Description display on the page and in HTML meta tags
#
title: GitHub Actions and Jenkins tool comparison
description: You can find a range of tools to support the CI/CD process. Jenkins and GitHub Actions outstandingly stand among them. This comparison will provide some insight to make the right choice for your process.
#
# Don't edit items below - they control the page layout
#
return-top: yes
layout: page
page-type: subpage
page-description: yes
permalink: /guides/tools/actions-v-jenkins
#
---
## GitHub Actions and Jenkins tool comparison

Jenkins and GitHub Actions both allow you to create workflows that automatically build, test, publish, release, and deploy code. Jenkins and GitHub Actions share some similarities in workflow configuration:

- Jenkins creates workflows using Declarative Pipelines, which are similar to GitHub Actions workflow files.
- Jenkins uses stages to run a collection of steps, while GitHub Actions uses jobs to group one or more steps or individual commands.
- Jenkins and GitHub Actions support container-based builds.
- Steps or tasks can be reused and shared with the community.

### Some key differences between GitHub Actions and Jenkins

- Jenkins has two types of syntax for creating pipelines: Declarative Pipeline and Scripted Pipeline. GitHub Actions uses YAML to create workflows and configuration files.
- Jenkins deployments are typically self-hosted, with users maintaining the servers in their own data centers. GitHub Actions offers a hybrid cloud approach by hosting its own runners that you can use to run jobs, while also supporting self-hosted runners.

### Common struggles with Jenkins that GitHub performs well at

- Keeping the plugins and the Jenkins server versions up to date can be tedious and difficult
- In Jenkins pipelines must be written in Groovy while GitHub can use Javascript, Typescript, Go, BASH, etc.
- Jenkins servers require server side setup and maintenance where github.com is managed for you

### Jenkins is a great choice when

- It is being used to deploy to production behind the company firewall

---

### Distributing your builds

Jenkins lets you send builds to a single build agent, or you can distribute them across multiple agents. You can also classify these agents according to various attributes, such as operating system types.

Similarly, GitHub Actions can send jobs to GitHub-hosted or self-hosted runners, and you can use labels to classify runners according to various attributes. The following table compares how the distributed build concept is implemented for both Jenkins and GitHub Actions.

| GitHub Actions | Jenkins |
| ----- | ----- |
| `runners`<br/> `self-hosted runners`| `agents` |

### Using sections to organize pipelines

Jenkins splits its Declarative Pipelines into multiple sections. Similarly, GitHub Actions organizes its workflows into separate sections. The table below compares Jenkins sections with the GitHub Actions workflow.

| GitHub Actions | Jenkins Directives |
| ----- | ----- |
| `jobs.<job_id>.runs-on`<br/> `jobs.<job_id>.container` | `agent` |
|| `post` |
| `jobs`| `stages` |
| `jobs.<job_id>.steps`| `steps` |

---

### More information

- [Examples of Common Tasks](https://docs.github.com/en/actions/learn-github-actions/migrating-from-jenkins-to-github-actions#examples-of-common-tasks)
- To search for existing Actions workflows or integrations go to the [GitHub Marketplace](https://github.com/marketplace)
- [Jenkins with GitHub](https://www.jenkins.io/solutions/github/)

---

[Return to Guides]({{ site.baseurl }}/guides)