---
title: ICorDebugStepper::SetInterceptMask 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: 9792abb4ee38a45aae59eaf79f1f0499539bd2ae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791770"
---
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask 方法
设置一个值，该值指定要单步执行的代码的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a>参数  
 `mask`  
 中CorDebugIntercept 枚举的值的组合，用于指定代码的类型。  
  
## <a name="remarks"></a>备注  
 如果设置了侦听器的位，则遇到给定类型的截取代码时，分档器将完成。 如果清除该位，则将跳过拦截代码。  
  
 `SetInterceptMask` 方法与[ICorDebugStepper：： SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) （来自用户的观点）之间可能存在不可预见的交互。 例如，如果类初始化代码的唯一可见部分（即非内部）缺少映射信息，并且未设置 STOP_NO_MAPPING_INFO （请参阅[ICorDebugStepper：： SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md)方法和 CorDebugUnmappedStop 枚举），则分档器将逐过程执行类初始化。 默认情况下，只会使用 `CorDebugIntercept` 枚举的 INTERCEPT_NONE 值。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
