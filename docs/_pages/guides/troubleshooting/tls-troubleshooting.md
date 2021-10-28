---
title: Troubleshooting TLS errors
layout: page
page-style: subpage
permalink: /tls-errors
modified-date: September 9, 2020
---

Refer to the section below for your tool to assist in resolving TLS errors when performing `git` operations.

## Git Bash

1. Launch Git Bash
1. Run these commands to configure `git` to trust the company's network.

```Bash
git config --global http.sslBackend schannel
git config --global credential.helper manager
git config --global http.schannelCheckRevoke best-effort
```

### Git for Windows before v2.27.0

Git versions before v2.27.0 do not have `best-effort` available as an option for `http.schannelCheckRevoke`.  Use `false` instead.

If you see an error like this:

```Bash
fatal: bad numeric config value 'best-effort' for 'http.schannelcheckrevoke': invalid unit
```

Run this command

```Bash
git config --global http.schannelCheckRevoke false
```

## Eclipse

See [Java TLS Errors]({{ site.baseurl }}/java-tls-errors) for a complete walkthrough with screenshots.

## Visual Studio

### Visual Studio 2019

1. In File Explorer, navigate to `C:\Program Files (x86)\Microsoft Visual Studio\2019\Professional\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer\Git\mingw32\bin`
   - NOTE: Your path may be slightly different based on the version of Visual Studio you have installed
1. Hold `Shift` and right click in the whitespace
1. Select **Open powershell window here** or **Open command prompt here**
1. Run these commands to configure `git` to trust the VA's network.

```Bash
.\git.exe config --global http.sslBackend schannel
.\git.exe config --global credential.helper manager
.\git.exe config --global http.schannelCheckRevoke false
```

### Visual Studio 2017

Visual Studio 2017 ships with a version of `git` that does not support disabling certificate revocation checks. We have to do a few extra steps to configure git properly.

#### Download your company's certificate

1. Download your company's certificate.
1. Move the downloaded file to `C:\Users\<USERNAME>\Documents\<CERT-FILE-NAME>.pem` where <USERNAME> is your own username and <CERT-FILE-NAME> is the PEM file you downloaded.

#### Configure git

1. In File Explorer, navigate to `C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer\Git\mingw32\bin`
   - NOTE: Your path may be slightly different based on the version of Visual Studio you have installed
1. Hold `Shift` and right click in the whitespace
1. Select **Open powershell window here** or **Open command prompt here**
1. Run these commands to configure `git` to trust the company's network. Remember to replace <USERNAME> with your own username and <CERT-FILE-NAME> is the PEM file you downloaded.

```Bash
.\git.exe config --global http.sslBackend openssl
.\git.exe config --global http.sslCAInfo "C:\Users\<USERNAME>\Documents\<CERT-FILE-NAME>.pem"
```

---

[Return to Guides]({{ site.baseurl }}/guides)