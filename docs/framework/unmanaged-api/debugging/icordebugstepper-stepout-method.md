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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419161"
---
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut 方法
导致此 ICorDebugStepper 到单步通过其包含线程，而若要完成在当前帧将控制权返回给调用的帧。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>备注  
 A`StepOut`操作将在正常情况下从返回当前帧到调用的帧后完成。  
  
 如果`StepOut`时，将调用在非托管代码中，该步骤将完成当前帧返回到调用它的托管代码时。  
  
 在.NET Framework 2.0 版中，请勿使用`StepOut`与 STOP_UNMANAGED 标志设置因为它将失败。 (使用[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)设置为单步执行的标志。)互操作调试程序必须单步执行到本机代码本身。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
