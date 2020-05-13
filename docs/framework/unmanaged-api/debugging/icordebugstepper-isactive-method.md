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
ms.openlocfilehash: faddf30248b58c68037635480d8977f22ad077d0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379024"
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
 弄`true`如果分档器当前正在执行步骤，则返回; 否则返回 `false` 。  
  
## <a name="remarks"></a>备注  
 任何步骤操作都保持活动状态，直到调试器接收到[ICorDebugManagedCallback：： StepComplete](icordebugmanagedcallback-stepcomplete-method.md)调用，这将自动停用分档器。 在达到回调条件之前，还可以通过调用[ICorDebugStepper：:D eactivate](icordebugstepper-deactivate-method.md)提前停用分档器。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
