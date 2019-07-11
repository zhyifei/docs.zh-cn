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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e1ace501bf5de741ea110fe4d3bb4bc44843bf8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760535"
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange 方法
导致此 ICorDebugStepper 单步执行其包含的线程，并返回到达超出指定范围的最后一个代码时。  
  
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
 [in]设置为`true`来单步执行的线程内调用的函数。 设置为`false`到逐过程执行函数。  
  
 `ranges`  
 [in]COR_DEBUG_STEP_RANGE 结构数组，其中每个指定的范围。  
  
 `cRangeCount`  
 [in] `ranges` 数组的大小。  
  
## <a name="remarks"></a>备注  
 `StepRange`方法的工作方式类似于[icordebugstepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)达到方法，只不过它给定范围之外的代码之前，无法完成。  
  
 这可以是单步执行一次一条指令比效率更高。 范围被指定为从一开始单步调试器的帧的偏移量对的列表。  
  
 范围是相对于一种方法的 Microsoft 中间语言 (MSIL) 代码。 调用[icordebugstepper:: Setrangeil](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)与`false`以便相对于一种方法的本机代码的范围。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
