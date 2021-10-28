---
#
# Editable - Title and Description display on the page and in HTML meta tags
#
title: Third Party Applications
description: Users can request 3rd party application access to the organization.  This is used for integrations with outside tools as well as other parts of GitHub.
#
# Don't edit items below - they control the page layout
#
return-top: yes
layout: page
page-description: yes
sidebar: guides
permalink: guides/org-admin/third-party-apps
#
---
*Note*: Official documentation is located [here](https://docs.github.com/en/github/setting-up-and-managing-organizations-and-teams/approving-oauth-apps-for-your-organization#:~:text=Under%20your%20organization%20name%2C%20click,requested%20application%2C%20click%20Grant%20access) and [here](https://docs.github.com/en/github/authenticating-to-github/connecting-with-third-party-applications).

### Finding Pending and Existing 3rd Party Application Integrations

* Open the [{{ site.org.name }}]({{ site.org.link }}) organization
* Navigate to *Settings*  
![settings location](imgs/3rd-party.1.png)
* Navigate to *3rd party access*  
<img src="imgs/3rd-party.2.png" width="25%" alt="3rd party access location">
* Applications pending review will be at the top of the page with the user that requested it next to the name
* Existing *approved* or *denied* applications will be listed below pending ones

### Approving or Denying 3rd Party Applications

* Select *review* on the application in question, notice the user that requested the application for further discussion if necessary  
<img src="imgs/3rd-party.3.png" width="75%" alt="review 3rd party application">
* Consider the data that the 3rd party will have access to and if that is acceptable and allowable within company policy.
* Click *grant access* or *deny this request*

---

[Return to Guides]({{ site.baseurl }}/guides)
