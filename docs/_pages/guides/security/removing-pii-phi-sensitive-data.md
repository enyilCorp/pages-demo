---
#
# Editable - Title and Description display on the page and in HTML meta tags
#
title: Removing PII, PHI, and sensitive data
description: Git is a version control system that will save the entire history of changes to files.  When PII, PHI, or sensitive data is committed you will need to follow the steps below to scrub it from the git database.

#
# Don't edit items below - they control the page layout
#
return-top: yes
layout: page
page-description: yes
sidebar: guides
permalink: guides/org-admin/removing-pii
#
---
*Note*: Official documentation is located [here](https://docs.github.com/en/github/authenticating-to-github/removing-sensitive-data-from-a-repository).  

## Removing PII and PHI

Git is a version control system that stores the history of all changes in a repository.  If PII/PHI is checked in to a repository, it cannot simply be deleted since a record of the changes will still reside in the `.git` folder for every time that the file was changed.

To fix this we will use a 3rd party open source tool called [`git filter-repo`](https://github.com/newren/git-filter-repo).  Git has an inbuilt facility to fix these, `filter-branch`, but it is not performant and has some undesired side effects so to the point that the [git maintainers suggest that it not be used.](https://git-scm.com/docs/git-filter-branch#_warning)

### Prerequisites

* Install [git filter-repo](https://github.com/newren/git-filter-repo/blob/main/INSTALL.md)
* Determine if the file(s) are tracked by Git LFS
  * `cat .gitattributes`  
  * If the file or file extension is in `.gitattributes` then it is tracked by Git LFS
  * Gather a list of the Git object id's for each file you are removing
    * `git ls-files -s path/to/file`  
    * This will return "[6 Digit permission] [41 Digit OID] [size of the file] [file name]"  you only need the 41 digit OID

### How to remove PII and PHI

* `git clone --mirror <repo> temp_name`
* `cd temp_name`
* `git filter-repo --path path/to/pii`
* `git push --mirror https://url/to/repo`
* Contact [GitHub Support](https://support.github.com/contact) or [GitHub Premium Support](https://premium.githubsupport.com/), asking them to remove cached views and references to the sensitive data in pull requests on GitHub.
  * If the file(s) are tracked in LFS provide the OID's to customer support and ask them to remove them as well
* Finally make sure all users of the repository rebase branches instead of merging them.  If they do not do this the old tainted history will get re-added
*See the [official docs](https://docs.github.com/en/github/authenticating-to-github/removing-sensitive-data-from-a-repository) for more details*

---

[Return to Guides]({{ site.baseurl }}/guides)
