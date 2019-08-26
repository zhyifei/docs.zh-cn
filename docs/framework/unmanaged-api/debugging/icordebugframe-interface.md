---
title: ICorDebugFrame 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4744ea67d0ce0d9ad2b13c45bdef65f884ef925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937006"
---
# <a name="icordebugframe-interface"></a>ICorDebugFrame 接口

表示当前堆栈上的帧。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateStepper 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|获取用于执行与此`ICorDebugFrame`相关的单步执行操作的 ICorDebugStepper。|  
|[GetCallee 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|获取一个指针, 该`ICorDebugFrame`指针指向此框架调用的当前链中的, 如果这是链中的最内层帧, 则返回 null。|  
|[GetCaller 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|获取指向当前链中`ICorDebugFrame`调用此帧的的指针, 如果这是链中最外层的帧, 则返回 null。|  
|[GetChain 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|获取一个指针, 该指针指向`ICorDebugFrame`作为的一部分的 ICorDebugChain。|  
|[GetCode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|获取一个指针, 该指针指向与此堆栈帧关联的 ICorDebugCode。|  
|[GetFunction 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|获取一个指向 ICorDebugFunction 的指针, 该指针包含与此堆栈帧关联的代码。|  
|[GetFunctionToken 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|获取包含与此堆栈帧关联的代码的函数的元数据标记。|  
|[GetStackRange 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|获取此`ICorDebugFrame`所表示的堆栈帧的绝对地址范围。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
