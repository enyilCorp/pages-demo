---
title: General Troubleshooting
layout: page
page-style: subpage
permalink: /general-troubleshooting
---

## Troubleshooting SSL connection errors

Because of the network configuration some companies, both GitHub Desktop and command line git clients occasionally have trouble cloning repositories.

The error may occur only when you're logged into the VPN, but when it occurs you'll see an error popup that mentions "certificate revocation":

![GitHub Desktop schannel error]({{ site.baseurl }}/guides/images/desktop-schannel-error.png)

The fix here is to update your Git configuration by adding the following lines to the `.gitconfig` file in your home directory.

- For details see [Certificate revocation check fails](https://github.com/desktop/desktop/blob/development/docs/known-issues.md#certificate-revocation-check-fails---3326) in the GitHub Desktop documentation.

```shell
[http]
  schannelCheckRevoke = false
```

Read on for specific instructions on how to do this, depending on which Git client you use. (Both of these do the same thing -- so you'll need to apply just one of these fixes.)

### Git for Windows or another command-line Git client

Start a command prompt or your Git shell and type the following command:

```shell
git config --global http.schannelCheckRevoke false
```

### GitHub Desktop

1. Launch **Wordpad**
2. **File > Open**
3. Navigate to your home directory -- which is typically `c:\Users\[YourUsername]`
4. Show all files
5. Select the GITCONFIG file named `.gitconfig`
  ![Wordpad find gitconfig]({{ site.baseurl }}/guides/images/wordpad-find-gitconfig.png)
  Windows won't show the filename, but it will be identified as a GITCONFIG type file
6. Add the following text, as shown highlighted in blue in the screenshot below:
  ```shell
  [http]
    schannelCheckRevoke = false
  ```
  ![Wordpad gitconfig edits]({{ site.baseurl }}/guides/images/wordpad-gitconfig-edits.png)
7. Save the file and quit Wordpad

Now launch GitHub Desktop and try to clone once again.

## Troubleshooting Eclipse eGit Channel Error

- eGit may refuse to clone a repository due to channel errors with no other information
- To fix this you will need to make sure that [Git Bash](https://gitforwindows.org/) is installed
- Check that you have a global git config
  - `git config --list --global`  
- If the above gives you an error, you will need to create a global config
  - `git config --global user.name "User Name"`
- Close and restart Eclipse and if this was your issue you will be able to clone

[Return to Guides]({{ site.baseurl }}/guides)
