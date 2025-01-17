---
title: "Email with Templates"
category: "Modules"
description: " "
tags: [ ]
draft: true
---

## 1 Introduction

The [E-mail with Templates](https://appstore.home.mendix.com/link/app/259/) module lets you send emails with templates. Email templates can be managed with the possibility of using tokens. With the tokens available in the email template, the attributes and references of an object are filled in automatically and correctly.

The typical usage scenario is sending emails with a template system and using tokens to handle all of your outgoing standard emails.

## 2 Configuration

To configure this module, follow these steps:

1. Download the [Mx Model Reflection](https://appstore.home.mendix.com/link/app/69/) module from the Mendix App Store.
2. Download and configure the [Encryption](https://appstore.home.mendix.com/link/app/1011/) module from the Mendix App Store.
3. Add the **Administration** snippet to a custom page in a different module.
4. View the example in the **USE_ME** > **Examples** folder.
5. Create a duplicate of this example in your own module and customize it to make it fit your needs:
	* `Sub_CreateAndQueueEmail` – this is preferred for normal environments and will send the email in the background using a scheduled event
	* `Sub_CreateAndSendEmail`  – this is preferred for [Free App](/deploy/mendix-cloud-deploy) environments and sends an email directly; this approach will block the user's flow and does not include a retry when the sending fails
	* `Post-deployment` – after deploying, you have to set up your email settings and insert your own email templates using the newly created navigation items under **Administrator**
6. Go to `MxObjects_Overview` and synchronize the objects. Make sure you do this every time you have added new objects.

## 3 Dependencies

### 3.1 Mendix Modules

* [Mx Model Reflection](https://appstore.home.mendix.com/link/app/69/)
* [Encryption](https://appstore.home.mendix.com/link/app/1011/)

### 3.2 Java Libraries

* *commons-codec-1.10.jar*
* *commons-email-1.3.1*
* *commons-email-1.4.0.jar*
* *com.sun.mail.javax.mail-1.4.5.jar*
* *javax.mail-1.6.0.jar*

## 4 Read More

* [Sending Email](/developerportal/deploy/sending-email)