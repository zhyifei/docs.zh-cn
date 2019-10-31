---
title: ICorDebugStepper::StepRange 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
ms.openlocfilehash: 2ca4542fe42fab0b5ff54b23b9492d3906698c10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120624"
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange 方法
使此 ICorDebugStepper 单步执行其包含线程，并在到达指定范围内的最后一个代码时返回。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a>参数  
 `bStepIn`  
 中设置为单步执行在线程中调用的函数的 `true`。 设置为 `false` 以逐过程执行函数。  
  
 `ranges`  
 中COR_DEBUG_STEP_RANGE 结构的数组，其中每个结构指定一个范围。  
  
 `cRangeCount`  
 [in] `ranges` 数组的大小。  
  
## <a name="remarks"></a>备注  
 `StepRange` 方法的工作方式类似于[ICorDebugStepper：： Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)方法，但直到到达给定范围之外的代码时才会完成。  
  
 这比单步执行一次指令更有效。 范围指定为自分档器帧开头的偏移量对的列表。  
  
 范围相对于方法的 Microsoft 中间语言（MSIL）代码。 调用[ICorDebugStepper：： SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)与 `false` 以使范围相对于方法的本机代码。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
