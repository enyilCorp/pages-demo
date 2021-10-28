---
#
# Editable - Title and Description display on the page and in HTML meta tags
#
title: Access Permissions on GitHub
description: Permissions can be given at the Enterprise level, Organization level, and Repository level. Some access permissions are best managed through teams.
#
# Don't edit items below - they control the page layout
#
return-top: yes
layout: page
page-type: subpage
page-description: yes

# same name for sidebar + pagination include
permalink: /guides/features/access-permissions
#
---
## Enterprise Level

At the enterprise level:

- __Owners__ have the ultimate power over the entire enterprise account and can take every action
- __Billing managers__ can manage the enterprise account's billing settings
- __Members__ and __outside collaborators__ of organizations belonging to your enterprise account are automatically members of the enterprise account, but have no access to the enterprise account itself or its settings. __Members__ are enabled to create private and internal repositories.

## Organization Level

At the organization level:

- __Owners__ have complete administrative access to the organization
- __Billing managers__ can manage billing settings for the organization
- __Member__ is the default role for everyone else; members should be organized using __teams__ for repository access

## Repository Level

At the repository level:

- __Admin__: Recommended for people who need full access to the project, including sensitive and destructive actions like managing security or deleting a repository
- __Maintain__: Recommended for project managers who need to manage the repository without access to sensitive or destructive actions
- __Write__: Recommended for contributors who actively push to your project
- __Triage__: Recommended for contributors who need to proactively manage issues and pull requests without write access
- __Read__: Recommended for non-code contributors who want to view or discuss your project

For a more granular breakdown of each level's ability to perform specific actions see the table [Repository access for each permission level](https://docs.github.com/en/github/setting-up-and-managing-organizations-and-teams/repository-permission-levels-for-an-organization#repository-access-for-each-permission-level) on [docs.github.com](https://docs.github.com/).

## Teams

Teams are groups of organization members that reflect the structure of your organization.

- Teams can nest other teams within them to further reflect the structure's hierarchy and offer cascading access permissions from the parent team to the child teams
- Permissions for teams is given by organization owners and __team maintainers__
- Teams can be visible or secret
  - Visible teams can be viewed and `@mentioned` by every organization member
  - Secret teams are visible to the people on the team and those with owner permissions
    - Secret teams are great for hiding teams with sensitive names or members
    - Secret teams cannot be nested or have child teams

## Repository Visibility

For enterprise accounts, repositories can be public, private, or internal. Your enterprise account is set so enterprise members can create private and internal repositories. Public repositories can only be created by enterprise or organization owners.

- __Public__: These repositories are accessible to everyone on the internet
- __Private__: Private repositories are only accessible to people with whom access is explicitly shared and certain organization members
- __Internal__: All enterprise members have read permissions to the internal repository
  - Internal repositories are not visible to people outside of the enterprise account, including outside collaborators on organization repositories
  - Internal repositories are great for practicing [innersource](https://resources.github.com/whitepapers/introduction-to-innersource/) within your enterprise account. Members of the enterprise can collaborate using open source methodologies without sharing information publicly.

---

[Return to Guides]({{ site.baseurl }}/guides)
