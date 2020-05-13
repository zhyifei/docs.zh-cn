---
title: ICorDebugManagedCallback::StepComplete 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 89b010706222ad44bccabd94191c42a888584944
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212654"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a>ICorDebugManagedCallback::StepComplete 方法
通知调试器某个步骤已完成。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a>参数  
 `pAppDomain`  
 中指向 ICorDebugAppDomain 对象的指针，该对象表示包含步骤已完成的线程的应用程序域。  
  
 `pThread`  
 中指向 ICorDebugThread 对象的指针，该对象表示步骤已完成的线程。  
  
 `pStepper`  
 中指向 ICorDebugStepper 对象的指针，该对象表示代码执行中的步骤。  
  
 `reason`  
 中CorDebugStepReason 枚举的值，该值指示单个步骤的结果。  
  
## <a name="remarks"></a>备注  
 如果需要，可以使用分档器继续单步执行，除非调试已终止。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugManagedCallback 接口](icordebugmanagedcallback-interface.md)
