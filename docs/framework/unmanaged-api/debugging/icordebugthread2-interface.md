---
title: ICorDebugThread2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82648714c375998e9daa1bb59cd9ebd9802b5794
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153928"
---
# <a name="icordebugthread2-interface"></a>ICorDebugThread2 接口
用作 ICorDebugThread 接口的逻辑扩展。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetActiveFunctions 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|获取包含有关线程的帧中的活动函数的数据的 COR_ACTIVE_FUNCTION 实例的数组。|  
|[GetConnectionID 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|获取此连接标识符`ICorDebugThread2`。|  
|[GetTaskID 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|获取此任务标识符`ICorDebugThread2`。|  
|[GetVolatileOSThreadID 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|获取此操作系统线程标识符`ICorDebugThread2`。|  
|[InterceptCurrentException 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|允许调试器来拦截上一个线程的当前异常。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
