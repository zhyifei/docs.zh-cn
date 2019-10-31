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
ms.openlocfilehash: 2d865f837d38894e8449af671e2d12e7676dd040
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129135"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>ICorDebugUnmanagedCallback::DebugEvent 方法
通知调试器已激发本机事件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a>参数  
 `pDebugEvent`  
 中指向本机事件的指针。  
  
 `fOutOfBand`  
 [in] `true`，如果在非托管事件发生后无法与托管进程状态交互，则在调试器调用[ICorDebugController：： Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)之前，否则，`false`。  
  
## <a name="remarks"></a>备注  
 如果正在调试的线程是 Win32 线程，请不要使用 Win32 调试接口的任何成员。 只能在 Win32 线程上调用 `ICorDebugController::Continue`，且仅当在带外事件继续时才调用。  
  
 `DebugEvent` 回调不遵循用于回调的标准规则。 调用 `DebugEvent`时，该进程将处于原始的 OS 调试停止状态。 将不同步该进程。 它将在必要时自动进入 "已同步" 状态以满足有关托管代码的信息请求，这可能会导致其他嵌套 `DebugEvent` 回调。  
  
 在进程上调用[ICorDebugProcess：： ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) ，以忽略异常事件，然后继续此过程。 调用此方法将在 CONTINUE 请求上发送 DBG_CONTINUE 而不是 DBG_EXCEPTION_NOT_HANDLED，并自动清除带外断点和单步例外。 即使在要调试的应用程序出现停止和已有的带内事件已存在时，也可以随时发出带外事件。  
  
 在 .NET Framework 版本2.0 中，调试程序应立即继续越过带外断点事件。 调试器应使用[ICorDebugProcess2：： SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)和[ICorDebugProcess2：： ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)方法添加和移除断点。 这些方法将自动跳过任何带外断点。 因此，调度的唯一的带外断点应该是已在指令流中的原始断点，如调用 Win32 `DebugBreak` 函数。 请勿尝试使用 `ICorDebugProcess::ClearCurrentException`、 [ICorDebugProcess：： GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)、 [ICorDebugProcess：： SETTHREADCONTEXT](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)或[调试 API](../../../../docs/framework/unmanaged-api/debugging/index.md)的任何其他成员。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugUnmanagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
