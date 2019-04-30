---
title: ICorDebugStepper::StepOut 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f663f5134cf34bf9beb66da20bbb5886baff5415
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987423"
---
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut 方法
导致此 ICorDebugStepper 单步执行其包含的线程，并完成时的当前帧将控制权返回给调用的帧。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>备注  
 一个`StepOut`操作将正常返回从当前帧的调用的帧后完成。  
  
 如果`StepOut`时，将调用在非托管代码中，该步骤完成后，将当前帧返回到调用它的托管代码。  
  
 在.NET Framework 2.0 版中，不要使用`StepOut`STOP_UNMANAGED 标志集因为这将会失败。 (使用[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)来设置标志的单步执行。)互操作调试程序必须跳出为本机代码本身。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
