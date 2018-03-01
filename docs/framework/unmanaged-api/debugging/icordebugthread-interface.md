---
title: "ICorDebugThread 接口 1"
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
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2df43a35e510695d7af0c38cbb8fb3b051f5f354
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread-interface1"></a>ICorDebugThread 接口 1
表示进程中的线程。 `ICorDebugThread` 实例的生存期与它表示的线程的生存期相同。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ClearCurrentException 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|未实现此方法。 请勿使用。|  
|[CreateEval 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|在此创建操作的 ICorDebugEval 对象`ICorDebugThread`。|  
|[CreateStepper 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|创建允许逐句通过在此活动帧的 ICorDebugStepper 对象`ICorDebugThread`。|  
|[EnumerateChains 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|为包含在此的所有堆栈链 ICorDebugChainEnum 枚举器获取的接口指针`ICorDebugThread`。|  
|[GetActiveChain 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|获取的接口指针到活动 ICorDebugChain 此`ICorDebugThread`。|  
|[GetActiveFrame 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|获取的接口指针到活动 ICorDebugFrame 此`ICorDebugThread`。|  
|[GetAppDomain 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|用于应用程序域中获取的接口指针，此`ICorDebugThread`当前正在执行。|  
|[GetCurrentException 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|获取一个表示当前由托管代码引发的异常的 ICorDebugValue 对象的接口指针。|  
|[GetDebugState 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|获取描述当前的调试状态的这一个 CorDebugThreadState 值`ICorDebugThread`。|  
|[GetHandle 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|获取当前句柄的活动部分`ICorDebugThread`。|  
|[GetID 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|获取此活动的部分的当前操作系统标识符`ICorDebugThread`。|  
|[GetObject 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|获取公共语言运行时 (CLR) 线程的接口指针。|  
|[GetProcess 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|此过程中获取的接口指针`ICorDebugThread`窗体一部分。|  
|[GetRegisterSet 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|获取与此关联的寄存器集的接口指针`ICorDebugThread`。|  
|[GetUserState 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|获取描述此的当前状态的 CorDebugUserState 值的按位组合`ICorDebugThread`。|  
|[SetDebugState 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|设置的按位组合`CorDebugThreadState`值，用于描述此的调试状态`ICorDebugThread`。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
