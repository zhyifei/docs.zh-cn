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
ms.openlocfilehash: ba138e79e0d6fb6f9c5e9c3efe3466f3c88cccae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782622"
---
# <a name="icordebugframe-interface"></a>ICorDebugFrame 接口

表示当前堆栈上的帧。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateStepper 方法](icordebugframe-createstepper-method.md)|获取一个 ICorDebugStepper，以执行与此 `ICorDebugFrame`相关的单步执行操作。|  
|[GetCallee 方法](icordebugframe-getcallee-method.md)|获取一个指针，该指针指向此框架调用的当前链中的 `ICorDebugFrame`，如果这是链中的最内层帧，则返回 null。|  
|[GetCaller 方法](icordebugframe-getcaller-method.md)|获取指向当前链中调用此帧的 `ICorDebugFrame` 的指针，如果这是链中最外层的帧，则返回 null。|  
|[GetChain 方法](icordebugframe-getchain-method.md)|获取一个指针，该指针指向 `ICorDebugFrame` 所属的 ICorDebugChain。|  
|[GetCode 方法](icordebugframe-getcode-method.md)|获取一个指针，该指针指向与此堆栈帧关联的 ICorDebugCode。|  
|[GetFunction 方法](icordebugframe-getfunction-method.md)|获取一个指向 ICorDebugFunction 的指针，该指针包含与此堆栈帧关联的代码。|  
|[GetFunctionToken 方法](icordebugframe-getfunctiontoken-method.md)|获取包含与此堆栈帧关联的代码的函数的元数据标记。|  
|[GetStackRange 方法](icordebugframe-getstackrange-method.md)|获取此 `ICorDebugFrame`所表示的堆栈帧的绝对地址范围。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
