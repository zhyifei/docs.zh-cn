---
title: ICorDebugStepper 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
ms.openlocfilehash: e9bb69567a247472af42efb08b609d3474c87ed2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791796"
---
# <a name="icordebugstepper-interface"></a>ICorDebugStepper 接口
表示在代码执行过程中由调试器执行的一个步骤。此步骤作为命令颁发和完成之间的标识符使用，可以实现取消对某个步骤的执行。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Deactivate 方法](icordebugstepper-deactivate-method.md)|使此 `ICorDebugStepper` 取消其收到的最后一个步骤命令。|  
|[IsActive 方法](icordebugstepper-isactive-method.md)|获取一个值，该值指示此 `ICorDebugStepper` 当前是否正在执行步骤。|  
|[SetInterceptMask 方法](icordebugstepper-setinterceptmask-method.md)|设置一个 CorDebugIntercept 值，该值指定要单步执行的代码的类型。|  
|[SetRangeIL 方法](icordebugstepper-setrangeil-method.md)|设置一个值，该值指示是否对[ICorDebugStepper：： StepRange](icordebugstepper-steprange-method.md)的调用传递参数值，这些值相对于本机代码或要逐步处理的方法的 Microsoft 中间语言（MSIL）代码。|  
|[SetUnmappedStopMask 方法](icordebugstepper-setunmappedstopmask-method.md)|设置一个 CorDebugUnmappedStop 值，该值指定将在其中停止执行的未映射代码的类型。|  
|[Step 方法](icordebugstepper-step-method.md)|使此 `ICorDebugStepper` 单步执行其包含线程，并根据需要继续单步执行线程中调用的函数。|  
|[StepOut 方法](icordebugstepper-stepout-method.md)|使此 `ICorDebugStepper` 单步执行其包含线程，并在当前帧将控件返回到调用帧时完成。|  
|[StepRange 方法](icordebugstepper-steprange-method.md)|使此 `ICorDebugStepper` 单步执行其包含线程，并在到达指定范围内的最后一个代码时返回。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugStepper` 接口具有以下用途：  
  
- 它充当发出的步骤命令与完成该命令之间的标识符。  
  
- 它提供一个中心接口，用于封装可执行的所有单步执行。  
  
- 它提供了一种提前取消单步执行操作的方法。  
  
 每个线程可以有多个分档器。 例如，在单步执行某个函数时可能会命中断点，用户可能希望在该函数中启动新的单步执行操作。 调试器负责确定如何处理这种情况。 调试器可能需要取消原始单步执行操作或嵌套两个操作。 `ICorDebugStepper` 接口支持这两种选择。  
  
 如果公共语言运行时（CLR）发出跨线程的已封送调用，则分档器可以在线程之间迁移。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
