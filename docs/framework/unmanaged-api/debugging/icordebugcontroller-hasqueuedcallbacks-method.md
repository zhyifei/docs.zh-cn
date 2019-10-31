---
title: ICorDebugController::HasQueuedCallbacks 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
ms.openlocfilehash: 51ee8b3631bffe9fd7fef4351e0aa67d1cbbe2c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125389"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks 方法
获取一个值，该值指示当前是否为指定线程排队任何托管回调。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>参数  
 `pThread`  
 中指向表示线程的 "ICorDebugThread" 对象的指针。  
  
 `pbQueued`  
 弄指向一个值的指针，该值在当前为指定线程排队时 `true` 的值;否则，`false`。  
  
 如果为 `pThread` 参数指定了 null，则如果当前存在托管的回调，则 `HasQueuedCallbacks` 会返回 `true`。  
  
## <a name="remarks"></a>备注  
 每次都将调度一个回调，每次调用[ICorDebugController：： Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 。 如果要报告同时发生的多个调试事件，则调试器可以检查此标志。  
  
 调试事件排队后，它们已发生，因此调试器必须释放整个队列，才能确保调试对象的状态。 （调用 `ICorDebugController::Continue` 以排出队列。）例如，如果队列在线程*x*上包含两个调试事件，并且调试器在第一个调试事件之后挂起线程*x* ，然后调用 `ICorDebugController::Continue`，则将调度线程*x*的第二个调试事件，但线程已暂停。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
