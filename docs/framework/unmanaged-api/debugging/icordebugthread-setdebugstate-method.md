---
title: "ICorDebugThread::SetDebugState 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.SetDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01f84c7126a4017a8d3b199f94eb497fae8e1a49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadsetdebugstate-method"></a>ICorDebugThread::SetDebugState 方法
设置描述此 ICorDebugThread 调试状态的标志。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a>参数  
 `state`  
 [in]指定此线程调试状态的 CorDebugThreadState 枚举值的按位组合。  
  
## <a name="remarks"></a>备注  
 `SetDebugState`设置线程的当前的调试状态。 （"当前调试状态"表示调试状态进程是否必须继续进行，不会在实际当前状态。）此标准的值是 THREAD_RUNNING。 只有调试器可能会影响线程调试状态。 调试状态执行上一次跨仍然存在，因此如果你想要保留的线程通过多个 thread_suspend 继续，你可以设置一次和以后便不必担心。 挂起线程和继续执行该过程可能会导致死锁，尽管通常可能性很小。 这是一种固有的质量的线程和进程，按设计。 调试器可以以异步方式中断和继续线程，以中断死锁。 如果线程的用户状态包括 USER_UNSAFE_POINT，该线程可能会阻止垃圾回收 (GC)。 这意味着挂起的线程具有更高版本可能导致死锁。 这可能会影响的调试事件已排入队列。 因此，调试器应耗尽整个事件队列 (通过调用[icordebugcontroller:: Hasqueuedcallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) 之前暂停或恢复线程。 否则，它可能认为它已有挂起的线程上获取事件。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
