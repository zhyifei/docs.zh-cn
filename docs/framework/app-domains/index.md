---
title: "使用应用程序域和程序集编程 | Microsoft Docs"
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
  - "应用程序域, 编程"
  - "程序集 [.NET Framework], 编程"
  - "编程应用程序域"
  - "编程程序集"
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 使用应用程序域和程序集编程
宿主（例如，Microsoft Internet Explorer、ASP.NET 和 Windows shell）将公共语言运行时加载到一个进程中，在该进程中创建[应用程序域](../../../docs/framework/app-domains/application-domains.md)，然后在运行 .NET Framework 应用程序时加载和执行该应用程序域中的用户代码。  多数情况下，您不需要考虑创建应用程序域以及将程序集加载到应用程序域中，因为运行时宿主会执行这些任务。  
  
 但是，如果要创建将承载公共语言运行时的应用程序，要创建以编程方式卸载的工具或代码，或者要创建可在不间断的状况下卸载和重新加载的可插接式组件，那么您就将创建自己的应用程序域。  即使不创建运行时宿主，本节提供的有关如何使用应用程序域和载入这些应用程序域中的程序集的信息也十分重要。  
  
## 本节内容  
 [应用程序域和程序集帮助主题](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 提供的链接指向在有关使用应用程序域和程序集编程的概念文档中找到的所有帮助主题。  
  
 [使用应用程序域](../../../docs/framework/app-domains/use.md)  
 提供创建、配置和使用应用程序域的示例。  
  
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 描述程序集上特性的创建、签名和设置过程。  
  
## 相关章节  
 [发出动态方法和程序集](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 描述如何创建动态程序集。  
  
 [公共语言运行时中的程序集](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 提供程序集的概念性概述。  
  
 [应用程序域](../../../docs/framework/app-domains/application-domains.md)  
 提供应用程序域的概念性概述。  
  
 [反射概述](../../../docs/framework/reflection-and-codedom/reflection.md)  
 描述如何使用 **Reflection** 类获取有关程序集的信息。