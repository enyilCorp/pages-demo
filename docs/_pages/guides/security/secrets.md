---
#
# Editable - Title and Description display on the page and in HTML meta tags
#
title: Secret Scanning
description: GitHub Advanced Security Secret Scanning scans repositories for known secret formats to prevent fraudulent use of credentials that were committed accidentally.
#
# Don't edit items below - they control the page layout
#
return-top: yes
layout: page
page-description: yes
sidebar: guides
permalink: guides/security/secrets
#
---

Every developer has to manage credentials. Secret scanning watches public and private repositories for known secret formats and immediately notifies either the secret provider or private repository admins when secrets are found.

<img src="https://octodex.github.com/images/hubot.jpg" align="right" height="250px">

If your project communicates with an external service, you might use a token or private key for authentication. Tokens and private keys are examples of secrets that a service provider can issue.

If you check a secret into a repository, anyone who has read access to the repository can use the secret to access the external service with your privileges. We recommend that you store secrets in a dedicated, secure location outside of the repository for your project.

Secret scanning happens by default on public repositories, and can be [enabled on private repositories](https://docs.github.com/en/github/administering-a-repository/configuring-secret-scanning-for-private-repositories) by repository administrators or organization owners.

## Actions to take

1. [Review service compatibility](https://docs.github.com/en/github/administering-a-repository/about-secret-scanning)
1. [Enable Secrets scanning on your repository](https://docs.github.com/en/github/administering-a-repository/configuring-secret-scanning-for-private-repositories#enabling-secret-scanning-for-private-repositories)

---

[Return to Guides]({{ site.baseurl }}/guides)
