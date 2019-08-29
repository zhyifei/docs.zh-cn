---
title: ICorDebugChain 接口
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93ada40bd88e53cd06f5e8d8136b2d527d7741e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969296"
---
# <a name="icordebugchain-interface"></a>ICorDebugChain 接口

表示一个物理或逻辑调用堆栈段。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumerateFrames 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|获取一个枚举数, 该枚举数包含链中所有托管堆栈帧 (从最新帧开始)。|  
|[GetActiveFrame 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|获取链上的活动 (即最近的) 帧。|  
|[GetCallee 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|获取此链调用的链。|  
|[GetCaller 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|获取调用此链的链。|  
|[GetContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|未实现。|  
|[GetNext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|获取线程的下一个帧链。|  
|[GetPrevious 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|获取线程的上一个帧链。|  
|[GetReason 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|获取此调用链的 genesis 的原因。|  
|[GetRegisterSet 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|获取此链的活动部分的寄存器集。|  
|[GetStackRange 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|获取此链的堆栈段的地址范围。|  
|[GetThread 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|获取此调用链所属的物理线程。|  
|[IsManaged 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|获取一个值, 该值指示此链是否正在运行托管代码。|  
  
## <a name="remarks"></a>备注  
 链中的堆栈帧占用连续堆栈空间并共享相同的线程和上下文。 链可以表示托管或非托管代码链。 空`ICorDebugChain`实例表示非托管代码链。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
