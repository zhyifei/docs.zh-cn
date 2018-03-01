---
title: "ICorDebugManagedCallback::DebuggerError 方法"
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
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc92bc6a1718d9d3505443e5b13786d1a359481f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>ICorDebugManagedCallback::DebuggerError 方法
通知调试器，在尝试处理来自公共语言运行时 (CLR) 的事件时发生错误。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pProcess`  
 [in]指向一个表示发生该事件的过程的"ICorDebugProcess"对象的指针。  
  
 `errorHR`  
 [in]从事件处理程序返回了 HRESULT 值。  
  
 `errorCode`  
 [in]一个整数，指定 CLR 错误。  
  
## <a name="remarks"></a>备注  
 该过程可能被放入传递模式，具体取决于错误的性质。  
  
 `DebugError`回调指示，调试服务已被禁用由于错误，因此调试器应提供错误消息给用户。 [Icordebugprocess:: Getid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)将安全地调用，但所有其他方法，包括[icordebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)，不应该调用。 调试器应使用操作系统工具来终止进程。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
