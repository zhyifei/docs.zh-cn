---
title: 安全 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d09b5b76c39f33848d44beb43d9b09c5e6ed13b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046175"
---
# <a name="security-etw-events"></a>安全 ETW 事件
<a name="top"></a> 在强名称验证和验证码验证期间会引发安全事件。  
  
 此类别包含以下事件：  
  
- [StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a>StrongNameVerificationStart_V1 和 StrongNameVerificationStop_V1 事件  
 下表显示了关键字和级别。 （有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）  
  
|引发事件的关键字|Level|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|信息性 (4)|  
  
 下表显示了事件信息。  
  
|Event|事件 ID|在发生以下情况时引发|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|强名称验证开始。|  
|`StrongNameVerificationStop_V1`|182|强名称验证结束。|  
  
 下表显示了事件数据。  
  
|字段名|数据类型|描述|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|验证标志。|  
|ErrorCode|win:UInt32|HResult 错误代码。|  
|FullyQualifiedAssemblyName|win:UnicodeString|完全限定程序集名称。|  
|ClrInstanceID|win:UInt16|CLR 或 CoreCLR 的实例的唯一 ID。|  
  
 [返回页首](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a>AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 事件  
 下表显示了关键字和级别。  
  
|引发事件的关键字|Level|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|信息性 (4)|  
  
 下表显示了事件信息。  
  
|Event|事件 ID|在发生以下情况时引发|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|验证码验证开始。|  
|`AuthenticodeVerificationStop_V1`|184|验证码验证结束。|  
  
 下表显示了事件数据。  
  
|字段名|数据类型|描述|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|验证标志。|  
|ErrorCode|win:UInt32|HResult 错误代码。|  
|ModulePath|win:UnicodeString|模块路径。|  
|ClrInstanceID|win:UInt16|CLR 或 CoreCLR 的实例的唯一 ID。|  
  
## <a name="see-also"></a>请参阅

- [CLR ETW 事件](clr-etw-events.md)
