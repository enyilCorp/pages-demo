---
#
# Editable - Title and Description display on the page and in HTML meta tags
#
title: User Invite Auditing
description: GitHub provides an audit log to Organization admins.  You can use this to review the users that have been recently invited.
#
# Don't edit items below - they control the page layout
#
return-top: yes
layout: page
page-description: yes
sidebar: guides
permalink: guides/org-admin/user-invite-audit
#
---
*Note*: Official documentation is located [here](https://docs.github.com/en/github/setting-up-and-managing-organizations-and-teams/reviewing-the-audit-log-for-your-organization).  

## Revewing the Audit Log

- Navigate to Settings
  ![Settings Location](imgs/3rd-party.1.png)
- Open the Audit Log
  <img src="imgs/audit-log.1.png" width="25%" alt="Audit log location">
- Search for user invites
  - Search for `action:org.invite_member`
    ![Audit log search](imgs/audit-log.2.png)
- Review the emails that have been invited for any inconsistencies
  - The log can also be used to find when a certain user was invited

---

[Return to Guides]({{ site.baseurl }}/guides)
