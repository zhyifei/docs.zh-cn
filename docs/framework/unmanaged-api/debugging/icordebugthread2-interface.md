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
ms.openlocfilehash: fdaad46b739721ff95b712d4b6461a793ae0a480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791420"
---
# <a name="icordebugthread2-interface"></a>ICorDebugThread2 接口
用作 ICorDebugThread 接口的逻辑扩展。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetActiveFunctions 方法](icordebugthread2-getactivefunctions-method.md)|获取 COR_ACTIVE_FUNCTION 实例的数组，这些实例包含有关线程帧中的活动函数的数据。|  
|[GetConnectionID 方法](icordebugthread2-getconnectionid-method.md)|获取此 `ICorDebugThread2`的连接标识符。|  
|[GetTaskID 方法](icordebugthread2-gettaskid-method.md)|获取此 `ICorDebugThread2`的任务标识符。|  
|[GetVolatileOSThreadID 方法](icordebugthread2-getvolatileosthreadid-method.md)|获取此 `ICorDebugThread2`的操作系统线程标识符。|  
|[InterceptCurrentException 方法](icordebugthread2-interceptcurrentexception-method.md)|允许调试器截获线程上的当前异常。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
