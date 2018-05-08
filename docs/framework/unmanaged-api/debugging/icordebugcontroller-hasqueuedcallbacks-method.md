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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eba265b727d00690ab77c6ae831e954d59df7c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks 方法
获取一个值，该值指示是否任何托管的回调当前正在排队等待指定的线程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pThread`  
 [in]指向一个表示线程的"ICorDebugThread"对象的指针。  
  
 `pbQueued`  
 [out]指向一个值，是`true`如果任何托管的回调目前排队指定线程; 否则为`false`。  
  
 如果为指定 null`pThread`参数，`HasQueuedCallbacks`将返回`true`托管的回调如果当前正在排队等待任何线程。  
  
## <a name="remarks"></a>备注  
 回调将调度一次一个地，每次[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)调用。 如果想要报告同时发生的多个调试事件，则调试器可以检查此标志。  
  
 调试事件排队时，它们已经发生，因此调试器必须耗尽整个队列，以确保的调试对象的状态。 (调用`ICorDebugController::Continue`清空队列。)例如，如果队列中包含两个线程上的调试事件*X*，调试器将暂停线程*X*后第一个调试事件，然后调用`ICorDebugController::Continue`，第二个调试事件线程*X*将进行调度，尽管线程已挂起。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 
