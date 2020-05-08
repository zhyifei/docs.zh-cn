---
title: ICorDebugController::SetAllThreadsDebugState 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: c2e8aaa2774e3e2699a73c40804391ca245047b1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976585"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>ICorDebugController::SetAllThreadsDebugState 方法
设置进程中所有托管线程的调试状态。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a>参数  
 `state`  
 中一个 "CorDebugThreadState" 枚举的值，该值指定线程的状态以进行调试。  
  
 `pExceptThisThread`  
 中一个指向 "ICorDebugThread" 对象的指针，该对象表示要从调试状态设置中免除的线程。 如果此值为 null，则不免除任何线程。  
  
## <a name="remarks"></a>备注  
 此`SetAllThreadsDebugState`方法可能会影响通过[EnumerateThreads 方法](icordebugcontroller-enumeratethreads-method.md)不可见的线程，因此，通过`SetAllThreadsDebugState`方法挂起的线程需要通过`SetAllThreadsDebugState`方法恢复。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅
