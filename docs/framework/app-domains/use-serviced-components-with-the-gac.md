---
title: "在服务组件中使用全局程序集缓存 | Microsoft Docs"
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
  - "程序集 [.NET Framework], 全局程序集缓存"
  - "GAC（全局程序集缓存）, 维护的组件"
  - "全局程序集缓存, 维护的组件"
  - "维护的组件, 全局程序集缓存"
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 在服务组件中使用全局程序集缓存
服务组件（托管代码 COM\+ 组件）应当放在全局程序集缓存中。  在有些方案中，公共语言运行时和 COM\+ 服务能够处理不在全局程序集缓存中的服务组件，而在有些方案中则不能。  以下方案对此进行了说明：  
  
-   对于 COM\+ Server 应用程序中的服务组件，包含组件的程序集必须在全局程序集缓存中，因为 Dllhost.exe 无法在服务组件所在的同一目录中运行。  
  
-   对于 COM\+ Library 应用程序中的服务组件，运行时和 COM\+ Services 可通过搜索当前目录来解析对组件所在程序集的引用。  在这种情况下，程序集不需要在全局程序集缓存中。  
  
-   对于 ASP.NET 应用程序中的服务组件，情况则有所不同。  如果将包含服务组件的程序集放在应用程序库的 bin 目录中，并使用按需注册，程序集将被影像复制到下载缓存，因为 ASP.NET 利用了运行时的影像功能。  
  
## 请参阅  
 [How to: Create a Serviced Component](http://msdn.microsoft.com/zh-cn/7ec0b488-e5fc-46f2-a48d-1278ea4e301d)   
 [使用程序集和全局程序集缓存](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md)   
 [Assembly Cache Viewer \(Shfusion.dll\)](http://msdn.microsoft.com/zh-cn/0d9464cf-ddba-4ca9-bbec-f678fb58f380)