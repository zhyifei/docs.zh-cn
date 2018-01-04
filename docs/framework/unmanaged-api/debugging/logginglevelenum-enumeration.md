---
title: "LoggingLevelEnum 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoggingLevelEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: LoggingLevelEnum
helpviewer_keywords: LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a1f8bb53d53593073df7ef7aa095eeb3b9f8c632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="logginglevelenum-enumeration"></a>LoggingLevelEnum 枚举
指示在托管线程记录事件时写入事件日志的描述性消息的严重级别。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`LTraceLevel0`|消息是跟踪级别 0。|  
|`LTraceLevel1`|消息是一个跟踪第 1 级。|  
|`LTraceLevel2`|消息是 2 的跟踪级别。|  
|`LTraceLevel3`|消息为 3 的跟踪级别。|  
|`LTraceLevel4`|消息是 4 的跟踪级别。|  
|`LStatusLevel0`|消息是状态级别 0。|  
|`LStatusLevel1`|消息是一个状态第 1 级。|  
|`LStatusLevel2`|消息是状态级别 2。|  
|`LStatusLevel3`|消息是状态级别 3。|  
|`LStatusLevel4`|消息是状态级别 4。|  
|`LWarningLevel`|消息是警告级别。|  
|`LErrorLevel`|消息是错误级别。|  
|`LPanicLevel`|消息是 panic 级别。|  
  
## <a name="remarks"></a>备注  
 公共语言运行时 (CLR) 调用[icordebugmanagedcallback:: Logmessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)方法，以通知调试器托管的线程记录事件。 CLR 中传递的值`LoggingLevelEnum`枚举，以指示托管的线程已写入到事件日志消息的严重性级别。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Diagnostics.EventLog>  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
