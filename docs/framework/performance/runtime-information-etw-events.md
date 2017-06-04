---
title: "运行时信息 ETW 事件 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ETW, 运行时信息事件"
  - "运行时信息事件 [.NET Framework]"
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# 运行时信息 ETW 事件
这些 ETW 事件记录有关运行时的信息，其中包括 SKU、版本号、运行时的激活方式、用于启动运行时的命令行参数、GUID（如果适用），以及其他相关的信息。  如果一个进程中执行多个运行时，则这些事件提供的信息 \(ClrInstanceID\) 可帮助消除运行时歧义。  
  
 下表显示两个运行时信息事件。  可以通过任何关键字或掩码引发这些事件。（有关详细信息，请参阅 [CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）  
  
|Event|事件 ID|提供程序|说明|  
|-----------|-----------|----------|--------|  
|`RuntimeInformationEvent`|187|CLRRuntime|加载运行时引发。|  
|`RuntimeInformationDCStart`|187|CLRRundown|枚举所加载的运行时。|  
  
 下表显示事件数据。  
  
|字段名|数据类型|说明|  
|---------|----------|--------|  
|ClrInstanceID|win:UInt16|CLR 或 CoreCLR 的实例的唯一 ID。|  
|Sku|win:UInt16|1 – 桌面 CLR。<br /><br /> 2 – CoreCLR。|  
|BclVersion – Major Version|win:UInt16|mscorlib.dll 的主版本号。|  
|BclVersion – Minor Version|win:UInt16|mscorlib.dll 的次版本号。|  
|BclVersion – 生成号|win:UInt16|mscorlib.dll 的生成号。|  
|BclVersion – QFE|win:UInt16|mscorlib.dll 的修补程序版本号。|  
|VMVersion – Major Version|win:UInt16|clr.dll 或 coreclr.dll 的版本号，具体取决于 SKU。|  
|VMVersion – Minor Version|win:UInt16|clr.dll 或 coreclr.dll 的次版本号，具体取决于 SKU。|  
|VMVersion – 生成号|win:UInt16|clr.dll 或 coreclr.dll 的生成号。|  
|VMVersion – QFE|win:UInt16|clr.dll 或 coreclr.dll 的修补程序版本号。|  
|StartupFlags|win:UInt32|mscoree.h 中定义的启动标志。|  
|StartupMode|win:UInt8|0x01 \- 托管的可执行文件。<br /><br /> 0x02 \- 承载的 CLR。<br /><br /> 0x04 \- C\+\+ 托管互操作。<br /><br /> 0x08 \- 已激活 COM。<br /><br /> 0x10 \- 其他。|  
|CommandLine|win:UnicodeString|仅当 StartupMode\=0x01 时才不为 null。|  
|ComObjectGUID|win:GUID|仅当 StartupMode\=0x08 时才不为 null。|  
|RuntimeDLLPath|win:UnicodeString|已加载到进程中的 CLR .dll 文件的路径。|  
  
## 请参阅  
 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)