---
title: "使用应用程序域 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "应用程序域，关于"
  - "公共语言运行时，应用程序域"
  - "运行时，应用程序域"
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 使用应用程序域
应用程序域为公共语言运行时提供隔离单元。  它们在进程中创建和运行。  应用程序域通常由运行时宿主创建，运行时宿主是负责将运行时载入进程并在应用程序域中执行用户代码的应用程序。  运行时宿主创建进程和默认应用程序域，并在其中运行托管代码。  运行时宿主包括 ASP.NET、Microsoft Internet Explorer 和 Windows shell。  
  
 对于多数应用程序，您不需要创建自己的应用程序域，运行时宿主将为您创建所有必要的应用程序域。  但是，如果您的应用程序需要隔离代码或使用并卸载 DLL，您可以创建并配置其他应用程序域。  
  
## 本节内容  
 [如何：创建应用程序域](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 描述如何以编程方式创建应用程序域。  
  
 [如何：卸载应用程序域](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 描述如何以编程方式卸载应用程序域。  
  
 [如何：配置应用程序域](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 提供配置应用程序域的简介。  
  
 [从应用程序域中检索安装程序信息](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 描述如何从应用程序域检索安装信息。  
  
 [如何：将程序集加载到应用程序域中](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 描述如何将程序集加载到应用程序域。  
  
 [如何：从程序集获得类型和成员信息](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 描述如何检索有关程序集的信息。  
  
 [影像复制程序集](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 描述如何通过影像复制在程序集正在使用时进行更新，以及如何配置影像复制。  
  
 [如何：接收首次异常通知](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 说明在公共语言运行时开始搜索异常处理程序之前，您如何接收已引发异常的通知。  
  
 [解决程序集加载问题](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 提供有关使用 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 事件处理程序集加载故障的指导。  
  
## 参考  
 <xref:System.AppDomain>  
 表示应用程序域。  提供用于创建和控制应用程序域的方法。  
  
## 相关章节  
 [公共语言运行时中的程序集](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 概述程序集执行的功能。  
  
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 描述程序集上特性的创建、签名和设置过程。  
  
 [发出动态方法和程序集](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 描述如何创建动态程序集。  
  
 [应用程序域](../../../docs/framework/app-domains/application-domains.md)  
 提供应用程序域的概念性概述。  
  
 [反射概述](../../../docs/framework/reflection-and-codedom/reflection.md)  
 描述如何使用 **Reflection** 类获取有关程序集的信息。