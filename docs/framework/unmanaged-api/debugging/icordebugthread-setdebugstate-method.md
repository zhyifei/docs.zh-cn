---
title: ICorDebugThread::SetDebugState 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
ms.openlocfilehash: b7678c64a085a0d4951d398595b9be89af8eeb6b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791441"
---
# <a name="icordebugthreadsetdebugstate-method"></a>ICorDebugThread::SetDebugState 方法
设置描述此 ICorDebugThread 的调试状态的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>参数  
 `state`  
 中CorDebugThreadState 枚举值的按位组合，用于指定此线程的调试状态。  
  
## <a name="remarks"></a>备注  
 `SetDebugState` 设置线程的当前调试状态。 （如果进程继续，则为 "当前调试状态"，而不是实际的当前状态。）此值的正常值为 THREAD_RUN。 只有调试器才能影响线程的调试状态。 调试状态完成最后一步，因此，如果想要使某个线程在多个继续 THREAD_SUSPENDed，则可以将其设置一次，这样就无需担心。 挂起线程并恢复进程可能会导致死锁，但通常不太可能。 这是线程和进程的内部质量，并按设计进行。 调试器可以异步中断和恢复线程以中断死锁。 如果线程的用户状态包括 USER_UNSAFE_POINT，则线程可能会阻止垃圾回收（GC）。 这意味着暂停的线程可能会导致死锁。 这不会影响已排队的调试事件。 因此，在挂起或恢复线程之前，调试程序应释放整个事件队列（通过调用[ICorDebugController：： HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)）。 否则，它可能会在其认为已挂起的线程上获取事件。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
