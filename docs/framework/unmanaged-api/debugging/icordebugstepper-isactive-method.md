---
title: ICorDebugStepper::IsActive 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: a242764710d92e81e8089bc2919734bfac4bcdb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137565"
---
# <a name="icordebugstepperisactive-method"></a>ICorDebugStepper::IsActive 方法
获取一个值，该值指示此 ICorDebugStepper 当前是否正在执行步骤。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a>参数  
 `pbActive`  
 弄如果分档器当前正在执行步骤，则返回 `true`;否则，将返回 `false`。  
  
## <a name="remarks"></a>备注  
 任何步骤操作都保持活动状态，直到调试器接收到[ICorDebugManagedCallback：： StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)调用，这将自动停用分档器。 在达到回调条件之前，还可以通过调用[ICorDebugStepper：:D eactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)提前停用分档器。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
