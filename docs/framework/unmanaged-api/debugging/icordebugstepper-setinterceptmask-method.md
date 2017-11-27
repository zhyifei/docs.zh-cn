---
title: "ICorDebugStepper::SetInterceptMask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetInterceptMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a99b504c0ce58ca6b89153667598cd4c2c682d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask 方法
设置一个值，指定的单步执行代码的类型。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a>参数  
 `mask`  
 [in]指定的代码类型 CorDebugIntercept 枚举的值的组合。  
  
## <a name="remarks"></a>备注  
 如果设置了拦截器位，遇到给定的类型的截获代码时，将完成分档器。 如果位将被清除，则将跳过截获的代码。  
  
 `SetInterceptMask`方法可能具有与出现未预见的交互[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) （从用户的角度来看）。 例如，如果仅可见 (即非内部) 类初始化代码部分中的缺少映射信息，因而 STOP_NO_MAPPING_INFO 未设置 (请参阅[icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)方法和CorDebugUnmappedStop 枚举） 分档器将逐过程执行类初始化。 默认情况下，只对 INTERCEPT_NONE 数值`CorDebugIntercept`将使用枚举。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
