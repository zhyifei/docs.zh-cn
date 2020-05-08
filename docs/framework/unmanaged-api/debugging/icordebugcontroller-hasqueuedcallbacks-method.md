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
ms.openlocfilehash: bd656445c2451d0583ddbc45e71c9e090bb80305
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892771"
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
 弄一个指向值的指针，该值`true`表示当前是否为指定线程将当前排队的任何托管回调;否则为`false`。  
  
 如果为该`pThread`参数指定了 null， `HasQueuedCallbacks`则将`true`返回，如果当前有托管的回调排队等候任何线程。  
  
## <a name="remarks"></a>备注  
 每次都将调度一个回调，每次调用[ICorDebugController：： Continue](icordebugcontroller-continue-method.md) 。 如果要报告同时发生的多个调试事件，则调试器可以检查此标志。  
  
 调试事件排队后，它们已发生，因此调试器必须释放整个队列，才能确保调试对象的状态。 （调用`ICorDebugController::Continue`以排出队列。）例如，如果队列在线程*x*上包含两个调试事件，并且调试器在第一个调试事件之后挂起线程*x* ，然后调用`ICorDebugController::Continue`，则线程*x*的第二个调试事件将被调度，但线程已挂起。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅
