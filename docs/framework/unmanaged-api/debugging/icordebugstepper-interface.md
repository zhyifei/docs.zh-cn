---
title: ICorDebugStepper 接口 1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 339b823e5e9f38ffd175c79e379e28ccc3565c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstepper-interface1"></a>ICorDebugStepper 接口 1
表示在代码执行过程中由调试器执行的一个步骤。此步骤作为命令颁发和完成之间的标识符使用，可以实现取消对某个步骤的执行。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Deactivate 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|这将导致`ICorDebugStepper`取消它收到的最后一个步骤命令。|  
|[IsActive 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|获取一个值，该值指示是否这`ICorDebugStepper`当前正在执行一个步骤。|  
|[SetInterceptMask 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|设置一个 CorDebugIntercept 值，指定的单步执行代码的类型。|  
|[SetRangeIL 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|设置一个值，该值指示是否调用[icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)传递自变量值相对于本机代码或单步执行的方法的 Microsoft 中间语言 (MSIL) 代码。|  
|[SetUnmappedStopMask 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|设置一个 CorDebugUnmappedStop 值，指定的顺序，则执行将暂停的非托管代码的类型。|  
|[Step 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|这将导致`ICorDebugStepper`到单步执行其包含的线程，以及 （可选） 到继续单步执行通过该线程中调用的函数。|  
|[StepOut 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|这将导致`ICorDebugStepper`到单步执行其包含线程和完成在当前帧将控制权返回给调用的帧。|  
|[StepRange 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|这将导致`ICorDebugStepper`到单步执行其包含的线程，并返回时达到超出指定范围的最后一个代码。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugStepper`接口具有以下用途：  
  
-   它充当步骤命令颁发和完成该命令之间的标识符。  
  
-   它提供了中央的接口来封装所有单步执行可执行。  
  
-   它使您能够过早地取消单步执行的操作。  
  
 可以有多个分档器每个线程。 例如，逐过程执行函数时可能会命中断点，用户可能想要启动新的单步执行操作，在该函数。 负责调试器来确定如何处理这种情况。 调试器可能想要取消原始单步执行的操作或嵌套的两个操作。 `ICorDebugStepper`接口支持这两种选择。  
  
 如果公共语言运行时 (CLR) 进行跨线程的封送调用，分档器可能迁移线程之间。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
