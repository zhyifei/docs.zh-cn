---
title: "如何：卸载应用程序域 | Microsoft Docs"
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
  - "Unload 方法"
  - "应用程序域，卸载"
  - "卸载应用程序域"
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 如何：卸载应用程序域
当您完成使用应用程序域时，可使用 [System.AppDomain.Unload](frlrfSystemAppDomainClassUnloadTopic) 方法将其卸载。  **Unload** 方法会正常关闭指定的应用程序域。  卸载过程中，没有新线程可以访问该应用程序域，并且会释放该应用程序域特定的所有数据结构。  
  
 加载到应用程序域中的所有程序集都会被移除，无法再使用。  如果应用程序域中的程序集不是特定于域的，则程序集的数据会保留在内存中，直到整个进程关闭。  除了关闭整个进程，没有机制可以卸载非特定于域的程序集。  在某些情况下，卸载应用程序域的请求不起作用，并导致 <xref:System.CannotUnloadAppDomainException>。  
  
 下面的示例新建名为 `MyDomain` 的应用程序域，并将一些信息输出至控制台，然后卸载应用程序域。  请注意，然后代码会尝试将卸载的应用程序域的友好名称输出至控制台。  此操作将生成由程序结尾处的 try\/catch 语句处理的异常。  
  
## 示例  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## 请参阅  
 [Programming with Application Domains](http://msdn.microsoft.com/zh-cn/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [如何：创建应用程序域](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)   
 [使用应用程序域](../../../docs/framework/app-domains/use.md)