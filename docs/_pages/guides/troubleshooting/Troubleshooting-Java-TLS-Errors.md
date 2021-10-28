---
title: Java TLS Errors
layout: page
page-style: subpage
permalink: /java-tls-errors
---

In some cases, your company may require outbound internet traffic to go through a proxy. Your Windows Desktop is configured to trust this proxy and usually most operations should succeed.

If you are encountering SSL/TLS errors when attempting to reach a resource on the internet (such as github.com), you need to configure Java to trust this proxy.

#### Download your company's certificate

1. Download your company's certificate.
1. Move the downloaded file to `C:\Users\<USERNAME>\Documents\<CERT-FILE-NAME>.pem` where <USERNAME> is your own username and <CERT-FILE-NAME> is the PEM file you downloaded.

## Find location of your Java Runtime Environment

1. Launch Eclipse
1. Navigate to Window > Preferences
   ![Eclipse Window > Preferences]({{ site.baseurl }}/guides/images/troubleshooting-java-tls/eclipse-step-1.png)
1. Navigate to Java > Installed JREs
   ![Eclipse Java > Installed JREs]({{ site.baseurl }}/guides/images/troubleshooting-java-tls/eclipse-step-2.png)
1. Open your active JRE
   ![Eclipse Open JRE]({{ site.baseurl }}/guides/images/troubleshooting-java-tls/eclipse-step-3.png)
1. Copy the path from JRE Home, we'll need it in a minute

## Update Java keystore with the company's certificate

1. Launch PowerShell (does not require admin rights unless your Java installation is in a protected location)
1. Run the following commands, replacing the parameters with yours

`cd "C:\Path\To\JRE\Home"`
`.\jre\bin\keytool.exe -import -alias company-certificate-authority -file "C:\Users\<USERNAME>\Documents\<CERT-FILE-NAME>.pem" -keystore .\jre\lib\security\cacerts -storepass changeit -noprompt`

![PowerShell Import Certificate]({{ site.baseurl }}/guides/images/troubleshooting-java-tls/ps-step-1.png)

Java should now trust your company's certificate authority, and your TLS issues should be resolved. 🎉

---

[Return to Guides]({{ site.baseurl }}/guides)
