---
title: "ICorDebugManagedCallback::StepComplete 方法"
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
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e7a09216284593c79c0cda6f5283ea8250678af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a>ICorDebugManagedCallback::StepComplete 方法
通知调试器已完成一个步骤。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAppDomain`  
 [in]指向一个表示包含该步骤已完成在其中的线程的应用程序域的 ICorDebugAppDomain 对象的指针。  
  
 `pThread`  
 [in]指向一个表示该步骤已完成在其中的线程的 ICorDebugThread 对象的指针。  
  
 `pStepper`  
 [in]指向一个表示在代码执行步骤的 ICorDebugStepper 对象的指针。  
  
 `reason`  
 [in]CorDebugStepReason 枚举，该值指示一个单步执行的结果的值。  
  
## <a name="remarks"></a>备注  
 分档器可能用于继续单步执行必要时，除非调试已终止。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
