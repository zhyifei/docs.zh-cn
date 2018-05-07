---
title: ICorDebugUnmanagedCallback::DebugEvent 方法
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51ccc7b1b50613f0d2b44a9e101314128782c412
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>ICorDebugUnmanagedCallback::DebugEvent 方法
通知调试器已激发本机事件。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pDebugEvent`  
 [in]本机事件指向的指针。  
  
 `fOutOfBand`  
 [in]`true`，如果与托管的进程状态的交互是不可能的非托管的事件发生，直到该调试器将调用后[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); 否则为`false`。  
  
## <a name="remarks"></a>备注  
 如果正在调试的线程的 Win32 线程，则不要使用调试接口的 Win32 任何成员。 你可以调用`ICorDebugController::Continue`仅 Win32 线程，仅当继续过去的带外事件。  
  
 `DebugEvent`回调不会不符合的回调的标准规则。 当调用`DebugEvent`，进程将在原始操作系统调试停止状态。 将不会同步过程。 它将自动进入时满足对托管代码，这可能会导致其他嵌套的相关信息的请求所需的同步的状态`DebugEvent`回调。  
  
 调用[icordebugprocess:: Clearcurrentexception](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)的过程将继续过程之前忽略异常事件。 调用此方法将工作表上继续请求，而不是 DBG_EXCEPTION_NOT_HANDLED DBG_CONTINUE，并自动清除的带断点和单步执行的异常。 即使正在调试的应用程序看上去已停止和未完成的带内事件已存在时，可以在任何时候，来自带外事件。  
  
 在.NET Framework 2.0 版中，调试器应立即跳过的带断点事件。 应使用调试器[icordebugprocess2:: Setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)和[icordebugprocess2:: Clearunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)方法来添加和删除断点。 这些方法将自动跳过任何带的断点。 因此，调度仅的带断点应已在指令流中，如调用 Win32 的原始断点`DebugBreak`函数。 不尝试使用`ICorDebugProcess::ClearCurrentException`， [icordebugprocess:: Getthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)， [icordebugprocess:: Setthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)，或任何其他成员的[调试 API](../../../../docs/framework/unmanaged-api/debugging/index.md)。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugUnmanagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
