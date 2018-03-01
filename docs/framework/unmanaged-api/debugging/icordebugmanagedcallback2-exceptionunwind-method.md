---
title: "ICorDebugManagedCallback2::ExceptionUnwind 方法"
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
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64b85311f625e39dd25c48a60dde2fbaf66a957f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a>ICorDebugManagedCallback2::ExceptionUnwind 方法
提供在异常展开过程中的状态通知。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAppDomain`  
 [in]指向一个表示包含引发异常的线程的应用程序域的 ICorDebugAppDomain 对象的指针。  
  
 `pThread`  
 [in]指向一个 ICorDebugThread 对象，表示引发异常的线程的指针。  
  
 `dwEventType`  
 [in]指定要发送信号的事件由回调在展开阶段 CorDebugExceptionUnwindCallbackType 枚举的值。  
  
 `dwFlags`  
 [in]值为[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)枚举，它指定有关异常的其他信息。  
  
## <a name="remarks"></a>备注  
 `ExceptionUnwind`在不同的时间点在过程中调用异常处理过程在展开阶段。 `ExceptionUnwind`可以同时展开一个异常不止一次调用。  
  
 如果`dwEventType`= DEBUG_EXCEPTION_INTERCEPTED，指令指针将叶帧中的线程，在之前的序列点 （这可能是之前的几种指令） 导致异常的说明。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugManagedCallback2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
