---
title: "安全 ETW 事件 | Microsoft Docs"
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
  - "ETW, 安全事件 (CLR)"
  - "安全事件 [.NET Framework]"
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# 安全 ETW 事件
<a name="top"></a> 在强名称验证和验证码验证期间会引发安全事件。  
  
 此类别包含以下事件：  
  
-   [StrongNameVerificationStart\_V1 和 StrongNameVerificationStop\_V1 事件](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [AuthenticodeVerificationStart\_V1 and AuthenticodeVerificationStop\_V1 事件](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## StrongNameVerificationStart\_V1 和 StrongNameVerificationStop\_V1 事件  
 下表显示了关键字和级别。 （有关详细信息，请参阅 [CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）  
  
|引发事件的关键字|级别|  
|--------------|--------|  
|`SecurityKeyword` \(0x400\)|信息性 \(4\)|  
  
 下表显示了事件信息。  
  
|Event|事件 ID|在发生以下情况时引发|  
|-----------|-----------|----------------|  
|`StrongNameVerificationStart_V1`|181|强名称验证开始。|  
|`StrongNameVerificationStop_V1`|182|强名称验证结束。|  
  
 下表显示了事件数据。  
  
|字段名|数据类型|说明|  
|---------|----------|--------|  
|VerificationFlags|win:UInt32|验证标志。|  
|ErrorCode|win:UInt32|HResult 错误代码。|  
|FullyQualifiedAssemblyName|win:UnicodeString|完全限定程序集名称。|  
|ClrInstanceID|win:UInt16|CLR 或 CoreCLR 的实例的唯一 ID。|  
  
 [返回页首](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## AuthenticodeVerificationStart\_V1 and AuthenticodeVerificationStop\_V1 事件  
 下表显示了关键字和级别。  
  
|引发事件的关键字|级别|  
|--------------|--------|  
|`SecurityKeyword` \(0x400\)|信息性 \(4\)|  
  
 下表显示了事件信息。  
  
|Event|事件 ID|在发生以下情况时引发|  
|-----------|-----------|----------------|  
|`AuthenticodeVerificationStart_V1`|183|验证码验证开始。|  
|`AuthenticodeVerificationStop_V1`|184|验证码验证结束。|  
  
 下表显示了事件数据。  
  
|字段名|数据类型|说明|  
|---------|----------|--------|  
|VerificationFlags|win:UInt32|验证标志。|  
|ErrorCode|win:UInt32|HResult 错误代码。|  
|ModulePath|win:UnicodeString|模块路径。|  
|ClrInstanceID|win:UInt16|CLR 或 CoreCLR 的实例的唯一 ID。|  
  
## 请参阅  
 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)