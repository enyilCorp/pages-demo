---
title: GitHub Teams
layout: page
page-style: subpage
permalink: /github-teams
---

## Teams

Teams are the best way to group users and provide access to repositories. Teams give you the ability to create groups of organization members with read, triage, write, maintain, or admin permissions to repositories that belong to the organization.

Teams are also central to many of GitHub's collaborative features, such as team @mentions, which notify appropriate groups of people that you'd like their input or attention. Teams can be both project or subject-matter focused, and can relate to job titles or roles. Teams are also useful for [CODEOWNERS][5] files to define and automate the pull request review process.

### Repository permission levels

Teams allow you to create groups with separate levels of access and visibility within an organization:

- **Read:** Recommended for non-code contributors who want to view or discuss your project
- **Triage:** Recommended for contributors who need to proactively manage issues and pull requests without write access
- **Write:** Recommended for contributors who actively push to your project
- **Maintain:** Recommended for project managers who need to manage the repository without access to sensitive or destructive actions
- **Admin:** Recommended for people who need full access to the project, including sensitive and destructive actions like managing security or deleting a repository

To read more granular action-availability information for each permission level, see [repository access for each permission level][4].

## Team maintainers

**Team maintainers** are primarily responsible for [adding][2] and [removing][3] team members day-to-day, as needed. Each team should have at least a couple team maintainers, but could need more depending on team size. Team maintains should know what they're responsible for, including adding another appropriate maintainer if they leave the team.

Members with team maintainer permissions can:

- Change the team's name and description
- Change the team's visibility
- Request to add a child team
- Request to add or change a parent team
- Set the team profile picture
- Edit team discussions
- Delete team discussions
- Add organization members to the team
- Remove organization members from the team
- Promote an existing team member to team maintainer
- Remove the team's access to repositories
- Manage code review assignment for the team
- Manage scheduled reminders for pull requests

## Adding and removing team members

A maintainer needs to know the team and the GitHub.com username of the person they want to add or remove. There is only one [removal][3] process, but there are two processes to add team members:

- [Adding users who are members of the {{ site.org.name }} organization](#adding-users-who-are-members-of-the-{{ site.org.name }}-organization)
- [Adding users who are not members of the {{ site.org.name }} organization](#adding-users-who-are-not-members-of-the-{{ site.org.name }}-organization)

### Adding users who are members of the {{ site.org.name }} organization

As long as the users are already a part of the {{ site.org.name }} organization on GitHub.com, team maintainers can [add them without needing help organization owners][1].

To **remove members** from a GitHub team, maintainers should:

1. Ensure they're in the `members` area
1. Search for the user or find them in the member list
1. Check the box to the left of their username
1. Click the dropdown for `member selected` at the top of the list
1. Click `Remove from team...`
1. Confirm the action by clicking `Remove members`

**Note:** You can remove multiple members at once by checking multiple boxes next to the appropriate usernames.

To **add members** to a GitHub team, maintainers should:

1. Ensure they're in the `members` area
1. Click on the `Add a Member` button at the top-right of the page
1. Enter the GitHub.com username of the person they wish to invite to the team
    - Ensure you have the correct username
    - You could search for the user's email (the user must have this email address associated with their account)

The invited user will get an email notifying them they have been invited to the team, and they must accept that invitation to complete the process.

### Adding users who are not members of the {{ site.org.name }} organization

If the users are not already members of the {{ site.org.name }} organization on GitHub.com, they will need to follow the process in [Getting Access to the organization]({{ site.baseurl }}/guides/onboarding/getting-access) guide.

When maintainers attempt to add users that are not a part of the organization, they will be notified when searching for that username:

![Message saying "Team members must already be part of the organization" when attempting to add a user that is not an org member]({{ site.baseurl }}/guides/features/imgs/team-management/team-management.png)

[1]: https://docs.github.com/en/articles/organizing-members-into-teams
[2]: https://docs.github.com/en/articles/adding-organization-members-to-a-team
[3]: https://docs.github.com/en/github/setting-up-and-managing-organizations-and-teams/removing-organization-members-from-a-team
[4]: https://docs.github.com/en/github/setting-up-and-managing-organizations-and-teams/repository-permission-levels-for-an-organization#repository-access-for-each-permission-level
[5]: https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/about-code-owners

---

[Return to Guides]({{ site.baseurl }}/guides)
