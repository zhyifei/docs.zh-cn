---
title: "ICorDebugManagedCallback2::MDANotification 方法"
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
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a58e286feb3387557d0a37c463f2af67abf8cc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>ICorDebugManagedCallback2::MDANotification 方法
提供了执行代码遇到的应用程序正在调试中的托管调试助手 (MDA) 的通知。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pController`  
 [in]ICorDebugController 接口公开进程或在其中发生 MDA 的应用程序域的指针。  
  
 调试器不应作出有关控制器是否为进程或应用程序域中，任何假设，尽管它始终可以查询该接口来做出决定。  
  
 `pThread`  
 [in]指向公开调试事件发生在其的托管的线程的 ICorDebugThread 接口的指针。  
  
 如果 MDA 出现在非托管线程的值`pThread`将为 null。  
  
 你必须从 MDA 对象本身中获取的操作系统 (OS) 线程 ID。  
  
 `pMDA`  
 [in]指向的指针[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)公开 MDA 信息的接口。  
  
## <a name="remarks"></a>备注  
 MDA 是启发式警告并且不需要任何显式调试器操作除外调用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)若要继续执行的应用程序正在调试。  
  
 公共语言运行时 (CLR) 可以确定要激发 Mda 哪些，以及哪些数据是在任意给定 MDA 在任何时间。 因此，调试器不应生成需要特定的 MDA 模式的任何功能。  
  
 Mda 可能排队，并可以激发不久后遇到 MDA。 如果运行时需要等待，直到它达到某一安全点中用于激发 MDA，而不是它遇到 MDA 时激发，则可能发生这种情况。 它还意味着，运行时可以激发一套排队的回调 （类似于"附加"事件操作） 的数字的 Mda。  
  
 调试器应释放对引用`ICorDebugMDA`后立即从返回的实例`MDANotification`回调，以允许 CLR 回收 MDA 占用的内存。 释放实例可能会提高性能，如果多个 Mda 还将触发。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [ICorDebugManagedCallback2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
