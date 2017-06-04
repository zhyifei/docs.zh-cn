---
title: "如何：配置应用程序域 | Microsoft Docs"
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
  - "应用程序域, 配置"
  - "ApplicationBase 属性"
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 如何：配置应用程序域
您可以使用 <xref:System.AppDomainSetup> 类为新应用程序域提供带有配置信息的公共语言运行时。  创建自己的应用程序域时，最重要的属性是 <xref:System.AppDomainSetup.ApplicationBase%2A>。  其他 **AppDomainSetup** 属性主要由运行时宿主用于配置特殊的应用程序域。  
  
 **ApplicationBase** 属性定义应用程序的根目录，  当运行时需要满足类型请求时，它在 **ApplicationBase** 属性指定的目录中探测包含该类型的程序集。  
  
> [!NOTE]
>  新的应用程序域只继承创建者的 **ApplicationBase** 属性。  
  
 下面的示例创建 **AppDomainSetup** 类的实例，此类用于创建新的应用程序域，将信息写入控制台，然后卸载应用程序域。  
  
## 示例  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## 请参阅  
 [Hosting Overview](http://msdn.microsoft.com/zh-cn/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/zh-cn/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [使用应用程序域](../../../docs/framework/app-domains/use.md)