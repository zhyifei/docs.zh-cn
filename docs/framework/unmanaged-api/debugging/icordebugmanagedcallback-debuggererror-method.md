---
title: ICorDebugManagedCallback::DebuggerError 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: c03be2405e1ab0287a2921b6e2e293862c67a193
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137377"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>ICorDebugManagedCallback::DebuggerError 方法
通知调试器在尝试处理来自公共语言运行时（CLR）的事件时出错。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>参数  
 `pProcess`  
 中一个指向 "ICorDebugProcess" 对象的指针，该对象表示发生事件的进程。  
  
 `errorHR`  
 中从事件处理程序返回的 HRESULT 值。  
  
 `errorCode`  
 中一个整数，指定 CLR 错误。  
  
## <a name="remarks"></a>备注  
 根据错误的性质，此过程可能会置于直通模式下。  
  
 `DebugError` 回调指示调试服务由于错误而被禁用，因此调试器应向用户提供错误消息。 [ICorDebugProcess：： GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)可以安全调用，但所有其他方法（包括[ICorDebug：： Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)）都不应调用。 调试器应使用操作系统工具来终止进程。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
