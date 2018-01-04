---
title: "ICorDebugStepper::StepRange 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a02efe1b701506cc3de695c5b79d5e9c84b25b8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange 方法
导致此 ICorDebugStepper 到单步执行其包含的线程，并返回在到达超出指定范围的最后一个代码时。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bStepIn`  
 [in]设置为`true`以单步执行线程中调用的函数。 设置为`false`以单步执行函数。  
  
 `ranges`  
 [in]COR_DEBUG_STEP_RANGE 结构数组，其中每个指定的范围。  
  
 `cRangeCount`  
 [in] `ranges` 数组的大小。  
  
## <a name="remarks"></a>备注  
 `StepRange`方法的工作原理类似[icordebugstepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)达到方法，只不过它给定范围之外的代码之前，无法完成。  
  
 这可能比单步执行一次一条指令更高效。 范围被指定为从单步调试器的帧的开头的偏移量对的列表。  
  
 范围都是方法的相对于 Microsoft 中间语言 (MSIL) 代码。 调用[icordebugstepper:: Setrangeil](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)与`false`以便相对于本机代码的方法的范围。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
