---
title: "CorDebugUserState 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 57fd9df27b1911c90bd11712b67e6e64588c2b5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuguserstate-enumeration"></a>CorDebugUserState 枚举
指示线程的用户状态。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>成员  
  
|值|描述|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|已请求的线程终止。|  
|`USER_SUSPEND_REQUESTED`|已请求线程的挂起。|  
|`USER_BACKGROUND`|在后台运行该线程。|  
|`USER_UNSTARTED`|线程开始执行。|  
|`USER_STOPPED`|线程已终止。|  
|`USER_WAIT_SLEEP_JOIN`|线程正在等待另一个线程来完成任务。|  
|`USER_SUSPENDED`|线程已挂起。|  
|`USER_UNSAFE_POINT`|该线程是一个不安全的点处。 也就是说，线程是执行在某个点中可能阻止垃圾回收。<br /><br /> 调试事件可能调度从不安全的点，但是挂起线程，将一个不安全的点处将很有可能导致死锁在恢复线程之前。 由实时 (JIT) 和垃圾回收实现确定的安全和不安全的点。|  
|`USER_THREADPOOL`|该线程是从线程池。|  
  
## <a name="remarks"></a>备注  
 用户状态是线程的时调试器检查该线程具有的状态。 一个线程可能具有用户状态的组合。  
  
 使用[icordebugthread:: Getuserstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)方法来检索线程的用户状态。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
