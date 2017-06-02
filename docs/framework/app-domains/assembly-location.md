---
title: "程序集位置 | Microsoft Docs"
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
  - "程序集 [.NET Framework], 位置"
  - "查找程序集"
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# 程序集位置
程序集的位置决定公共语言运行时是否可以在引用时找到程序集，也可以决定程序集是否可与其他程序集共享。  您可以在以下位置部署程序集：  
  
-   应用程序的目录或子目录。  
  
     这是部署程序集最常用的位置。  应用程序根目录的子目录可以基于语言或区域性。  如果程序集具有区域特性中的信息，则它必须位于带有区域性名称的应用程序目录下的子目录中。  
  
-   全局程序集缓存。  
  
     这是安装于公共语言运行时安装位置的计算机内的代码缓存。  大多数情况下，如果要与多个应用程序共享程序集，则应将程序集部署到全局程序集缓存中。  
  
-   在 HTTP 服务器上。  
  
     部署在 HTTP 服务器上的程序集必须具有强名称，请在应用程序配置文件的基本代码区域中指向此程序集。  
  
## 请参阅  
 [创建程序集](../../../docs/framework/app-domains/create-assemblies.md)   
 [全局程序集缓存](../../../docs/framework/app-domains/gac.md)   
 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)