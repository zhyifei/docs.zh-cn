---
title: "如何：从程序集获得类型和成员信息 | Microsoft Docs"
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
  - "程序集 [.NET Framework], 获取信息"
  - "获取程序集信息"
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 如何：从程序集获得类型和成员信息
<xref:System.Reflection> 命名空间中包含了许多从程序集中获取信息的方法。  本节介绍其中的一种。  有关其他信息，请参见[反射概述](../../../docs/framework/reflection-and-codedom/reflection.md)。  
  
 下面的示例从程序集中获取类型和成员信息。  
  
## 示例  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## 请参阅  
 [Hosting Overview](http://msdn.microsoft.com/zh-cn/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/zh-cn/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [反射](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [使用应用程序域](../../../docs/framework/app-domains/use.md)