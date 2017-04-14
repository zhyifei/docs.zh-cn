---
title: "如何：创建应用程序域 | Microsoft Docs"
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
  - "应用程序域，创建"
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 如何：创建应用程序域
当需要应用程序域时，公共语言运行时宿主会自动创建它们。  不过，您可以创建自己的应用程序域并将它们加载到需要亲自管理的程序集中。  您也可以创建从中执行代码的应用程序域。  
  
 若要创建新的应用程序域，可使用 <xref:System.AppDomain?displayProperty=fullName> 类中某个重载的 **CreateDomain** 方法。  您可以为应用程序域命名并按该名称来引用应用程序域。  
  
 下面的示例创建新的应用程序域，并为它指定名称 `MyDomain`，然后将宿主域的名称和新创建的子应用程序域输出到控制台。  
  
## 示例  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## 请参阅  
 [Hosting Overview](http://msdn.microsoft.com/zh-cn/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/zh-cn/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [使用应用程序域](../../../docs/framework/app-domains/use.md)