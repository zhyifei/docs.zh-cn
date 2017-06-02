---
title: "从应用程序域中检索安装程序信息 | Microsoft Docs"
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
  - "AppDomainSetup 对象"
  - "应用程序域, 检索安装信息"
  - "检索安装信息"
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 从应用程序域中检索安装程序信息
应用程序域的每个实例同时包含属性和 <xref:System.AppDomainSetup> 信息。  您可以使用 <xref:System.AppDomain?displayProperty=fullName> 类从应用程序域中检索安装信息。  此类提供了几个检索有关应用程序域的配置信息的成员。  
  
 您也可以查询应用程序域的 **AppDomainSetup** 对象，获取创建该对象时传递至域的安装信息。  
  
 下面的示例创建新的应用程序域，然后将几个成员值输出至控制台。  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 下面的示例设置并检索应用程序域的安装信息。  请注意，`AppDomain.SetupInformation.ApplicationBase` 获取配置信息。  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## 请参阅  
 [Hosting Overview](http://msdn.microsoft.com/zh-cn/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/zh-cn/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [使用应用程序域](../../../docs/framework/app-domains/use.md)