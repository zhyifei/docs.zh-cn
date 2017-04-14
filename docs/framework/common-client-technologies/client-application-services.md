---
title: "客户端应用程序服务 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "应用程序设置, 客户端应用程序服务"
  - "ASP.NET 服务, 客户端应用程序服务"
  - "身份验证 [ASP.NET], 客户端应用程序服务"
  - "客户端应用程序服务"
  - "客户端应用程序服务, 关于客户端应用程序服务"
  - "客户端应用程序, ASP.NET 服务"
  - "凭据 [.NET Framework]"
  - "登录 [客户端应用程序服务]"
  - "配置文件 [ASP.NET], 客户端应用程序服务"
  - "基于角色的安全性 [.NET Framework], 客户端应用程序服务"
  - "角色 [.NET Framework], 客户端应用程序服务"
  - "共享信息和功能 [客户端应用程序服务]"
  - "Web 设置 [客户端应用程序服务]"
  - "基于 Windows 的应用程序, 客户端应用程序服务"
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 客户端应用程序服务
客户端应用程序服务让你可以轻松使用 Microsoft ASP.NET 2.0 AJAX Extensions 中包含的 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 登录名、角色和配置文件应用程序服务，创建基于 Windows 的应用程序。  这些服务使多个基于 Web 和 Windows 的应用程序共享来自单个服务器的用户信息和用户管理功能。  例如，你可以使用这些服务来执行下列任务：  
  
-   对用户进行身份验证。  你可以使用身份验证服务验证用户的身份。  
  
-   确定经身份验证的用户的角色。  你可以根据用户的角色使用角色服务来更改应用程序的用户界面。  例如，你可以为管理员角色的用户提供其他功能。  
  
-   存储和访问位于服务器上的每用户应用程序设置。  你可以使用 Web 设置服务（也称为配置文件服务）跨多个应用程序和位置共享设置。  
  
 客户端应用程序服务通过可在应用程序配置文件中指定的客户端服务提供程序来利用 Web 服务扩展性模型。  网络连接不可用时，这些服务提供程序包括使用本地缓存进行身份验证、角色和设置数据等脱机功能。  
  
 有关 [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] 应用程序服务的详细信息，请参阅 [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md)。  
  
## 本节内容  
 [客户端应用程序服务概述](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 介绍可通过客户端应用程序服务提供程序提供的功能。  
  
 [如何：配置客户端应用程序服务](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 介绍如何使用 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 项目设计器启用并配置应用程序服务。  还介绍了对 App.config 文件的相应更改。  
  
 [如何：使用客户端应用程序服务来实现用户登录](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 介绍如何在应用程序配置为使用客户端身份验证服务提供程序时验证用户。  
  
 [演练：使用客户端应用程序服务](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 介绍如何在单个应用程序中合并所有客户端应用程序服务功能。  本演练提供了端到端指导。  例如，它包括有关如何创建可用于测试客户端应用程序服务的 ASP.NET Web 服务应用程序的说明。  
  
## 参考  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## 请参阅  
 [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md)   
 [Using Forms Authentication with Microsoft Ajax](../Topic/Using%20Forms%20Authentication%20with%20Microsoft%20Ajax.md)   
 [Using Roles Information with Microsoft Ajax](../Topic/Using%20Roles%20Information%20with%20Microsoft%20Ajax.md)   
 [Using Profile Information with Microsoft Ajax](../Topic/Using%20Profile%20Information%20with%20Microsoft%20Ajax.md)   
 [ASP.NET Authentication](../Topic/ASP.NET%20Authentication.md)   
 [Managing Authorization Using Roles](../Topic/Managing%20Authorization%20Using%20Roles.md)   
 [OLD NIB: Managing Application Settings](http://msdn.microsoft.com/zh-cn/7de3c3bd-e0dc-4e75-a1aa-7b0ecfaac4fc)   
 [应用程序设置概述](../../../docs/framework/winforms/advanced/application-settings-overview.md)