---
title: "Web 设置架构 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "ASP.NET 配置系统, Web 设置架构"
  - "配置文件 [ASP.NET]"
  - "配置架构 [.NET Framework], Web 设置"
  - "架构 Web 设置"
  - "Web 设置, 架构 [ASP.NET]"
  - "Web.config 配置文件 [ASP.NET]"
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Web 设置架构
Web 设置可指定适用于由 ASP.NET 承载层管理的进程范围的行为的 CPU 和执行级 ASP.NET 设置。  这些设置不同于应用程序域类型的设置，后者是在 ASP.NET 应用程序的 Web.config 文件中指定的。  
  
 Web 设置包含在 Aspnet.config 文件中，这些文件位于各个版本的 .NET Framework 的安装文件夹中。  例如，[!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]的 Aspnet.config 文件位于以下文件夹中：  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 Web 设置不会在任何其他配置文件中使用，如 machine.config 文件、根 Web.config 或应用程序级 Web.config 文件。  
  
 [\<configuration\> 元素](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.web\> 元素（Web 设置）](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [\<applicationPool\> 元素（Web 设置）](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|元素|说明|  
|--------|--------|  
|[\<system.web\>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|包含 ASP.NET 承载层使用的信息。|  
|[\<applicationPool\>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|指定适用于由 ASP.NET 承载层管理的进程范围的行为的 CPU 和执行级 ASP.NET 设置。|  
  
## 请参阅  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)