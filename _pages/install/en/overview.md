---
layout: page
title: System overview
permalink: "install/en/overview/"
language: en
---

OneOffixx contains multiple components that can be divided into two categories:

On one hand there are __server-side applications__ and on the other hand there is the __Windows client__ and its __Office add-ins__.

![x]({{ site.baseurl }}/assets/content-images/install/en/install-overview.png "Install components - overview")

## <i class="fa fa-server" aria-hidden="true"></i> Server-side applications

OneOffixx stores all of its server-side data in a __SQL database__. This data is provided by an API Service to the Windows client for synchronization. Furthermore, a number of additional components are supplied:

* IIS-Web-applications:
  * __Service:__ Includes the SOAP Service for Client Synchronization.
  * __Admin:__ This application provides support during the operation and contains several tools to access and edit data. Moreover, statistical data about available templates is displayed here.
  * __Web:__ Enables users to create documents in their browser or to display on overview of the existing templates.
  * __Hub:__ Creates a communication channel between Service, Hub, and Admin.
* Services and utilities:
  * __User Sync Worker:__ This application allows the synchronization of user profiles and user data with the Active Directory or another LDAP system.

For more information regarding the installation visit __[Server Installation]({{ site.baseurl }}/install/en/server)__. 

## <i class="fa fa-desktop" aria-hidden="true"></i> Windows Client & Office Add-Ins

The Windows Client offers various functions for the normal user, template creator, or administrator. For more information regarding the installation visit __[Client Installation]({{ site.baseurl }}/install/en/client)__. 

{% include alert.html type="info" text="To learn more about of the use of OneOffixx utilize our <b><a href='http://help.oneoffixx.com/suite/en/'>Online Help</a></b>." %}

The client retrieves data from OneOffixx service through the __API service__ and stores it in a __local Cache__. Office add-ins __connect with the installed client__ once they are installed.

## <i class="fa fa-building-o" aria-hidden="true"></i> Citrix TS/XenApp, Microsoft Terminal Server

Information about the client installation on the Microsoft Terminal Server or the Citrix Ts/Xenapp is provided at __[OneOffixx Citrix/Terminal Server Installation]({{ site.baseurl }}/install/en/client-citrix-ts)__.

