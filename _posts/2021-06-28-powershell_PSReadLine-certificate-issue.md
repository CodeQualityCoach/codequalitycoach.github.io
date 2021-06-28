---
layout: post
title: Powershell 7 and "Trusted Publishers"
categories: [EN, Powershell]
tags: [Powershell, Certificate, Trusted Publishers]
---

## Untrusted Publishers

Recently, I installed `Powershell 7` and was using it for a while. After settings my code security to AllSigned, I got the following error.

> File C:\program files\powershell\7\Modules\PSReadLine\PSReadLine.format.ps1xml is published by CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US and is not trusted on your system. Only run scripts from trusted publishers.

This is a little bit annoying because the module is signed so it should work. Powershell shows the following error message.

![Powershell 7 Error](/assets/posts/2021-06-28-powershell_PSReadLine-certificate-issue_01.png)

## Trust the Publisher

To trust the publisher, the certificate must be added to users or machines certificate store in "Trusted Publishers". But hot to get the certificate?

The certificate can be found in `C:\program files\powershell\7\Modules\PSReadLine\PSReadLine.cat`. With opening the file, select `View Signature` and click `View Certificate`. This dialogue provides the option `Install Certificate` to the "Trusted Publishers".

![Install Certificate](/assets/posts/2021-06-28-powershell_PSReadLine-certificate-issue_03.png)

After adding the certificate, Powershell loads the module without any questions.

![Powershell 7 Is Happy](/assets/posts/2021-06-28-powershell_PSReadLine-certificate-issue_02.png)
