---
title: "ICorDebugStepper::IsActive 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd919852d3e7c187dff7fc4304d0a1b42f5294e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperisactive-method"></a>ICorDebugStepper::IsActive 方法
获取一个值，该值指示是否此 ICorDebugStepper 当前正在执行一个步骤。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbActive`  
 [out]返回`true`如果分档器当前正在执行一个步骤; 否则，返回`false`。  
  
## <a name="remarks"></a>备注  
 任何步骤操作保持活动状态，直至调试器收到[icordebugmanagedcallback:: Stepcomplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)调用，这可以自动将分档器停用。 分档器可能还停用过早地通过调用[icordebugstepper:: Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)在回调之前条件为止。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
