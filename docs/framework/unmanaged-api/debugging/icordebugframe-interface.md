---
title: ICorDebugFrame 接口 1
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
ms.openlocfilehash: 7f160612e499ca7bd2185c95aa07a3784c5a4a19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635742"
---
# <a name="icordebugframe-interface1"></a>ICorDebugFrame 接口 1
表示当前堆栈上的帧。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateStepper 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|获取执行单步执行操作相对于此 ICorDebugStepper `ICorDebugFrame`。|  
|[GetCallee 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|获取一个指向`ICorDebugFrame`此帧调用，或如果此将返回 null 是链中的最内部帧的当前链中。|  
|[GetCaller 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|获取一个指向`ICorDebugFrame`当前链中调用此帧，或如果此将返回 null 是链中的最外面的帧。|  
|[GetChain 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|获取一个指向 ICorDebugChain 此`ICorDebugFrame`是的一部分。|  
|[GetCode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|获取一个指向与此堆栈帧关联 ICorDebugCode。|  
|[GetFunction 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|获取一个指针指向包含与此堆栈帧关联的代码 ICorDebugFunction。|  
|[GetFunctionToken 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|获取包含与此堆栈帧关联的代码的函数的元数据标记。|  
|[GetStackRange 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|获取表示此堆栈帧的绝对地址范围`ICorDebugFrame`。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
