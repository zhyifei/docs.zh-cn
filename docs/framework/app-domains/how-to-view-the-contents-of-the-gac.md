---
title: "如何：查看全局程序集缓存的内容 | Microsoft Docs"
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
  - "GAC（全局程序集缓存）, 查看内容"
  - "Gacutil.exe"
  - "“全局程序集缓存”工具"
  - "全局程序集缓存, 查看内容"
  - "全局程序集缓存中的程序集列表"
  - "具有强名称的程序集, 全局程序集缓存"
  - "查看全局程序集缓存中的程序集"
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 如何：查看全局程序集缓存的内容
使用[全局程序集缓存工具 \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 可查看全局程序集缓存的内容。  
  
### 查看全局程序集缓存中的程序集列表  
  
1.  在 [Visual Studio 命令提示符](../../../docs/framework/tools/developer-command-prompt-for-vs.md)处，键入下列命令：  
  
     **gacutil \-l**   
     \- 或 \-               
     **gacutil \/l**  
  
 在 .NET Framework 的早期版本中，可以通过 [Shfusion.dll](http://msdn.microsoft.com/zh-cn/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell 扩展在文件资源管理器中查看全局程序集缓存。  从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，Shfusion.dll 已过时。  
  
## 请参阅  
 [使用程序集和全局程序集缓存](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md)