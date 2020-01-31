---
title: ICorDebugManagedCallback 接口
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback
helpviewer_keywords:
- ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: b47f1d61-c7dc-4196-b926-0b08c94f7041
topic_type:
- apiref
ms.openlocfilehash: 9a33b90bf39103756ab4fd07157739633997fb61
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788403"
---
# <a name="icordebugmanagedcallback-interface"></a>ICorDebugManagedCallback 接口
提供用于处理调试器回调的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Break 方法](icordebugmanagedcallback-break-method.md)|当执行代码流中的 <xref:System.Reflection.Emit.OpCodes.Break> 指令时，通知调试器。|  
|[Breakpoint 方法](icordebugmanagedcallback-breakpoint-method.md)|遇到断点时，通知调试器。|  
|[BreakpointSetError 方法](icordebugmanagedcallback-breakpointseterror-method.md)|通知调试器，公共语言运行时（CLR）无法准确绑定在实时（JIT）编译函数之前设置的断点。|  
|[ControlCTrap 方法](icordebugmanagedcallback-controlctrap-method.md)|通知调试器在被调试的进程中捕获了 CTRL + C。|  
|[CreateAppDomain 方法](icordebugmanagedcallback-createappdomain-method.md)|通知调试器已创建应用程序域。|  
|[CreateProcess 方法](icordebugmanagedcallback-createprocess-method.md)|第一次附加或启动进程时，通知调试器。|  
|[CreateThread 方法](icordebugmanagedcallback-createthread-method.md)|通知调试器线程已开始执行托管代码。|  
|[DebuggerError 方法](icordebugmanagedcallback-debuggererror-method.md)|通知调试器在尝试处理来自 CLR 的事件时出错。|  
|[EditAndContinueRemap 方法](icordebugmanagedcallback-editandcontinueremap-method.md)|已否决。 通知调试器已将重新映射事件发送到 IDE。|  
|[EvalComplete 方法](icordebugmanagedcallback-evalcomplete-method.md)|通知调试器已完成计算。|  
|[EvalException 方法](icordebugmanagedcallback-evalexception-method.md)|通知调试器由于未处理的异常而终止了计算。|  
|[Exception 方法](icordebugmanagedcallback-exception-method.md)|通知调试器已从托管代码引发了异常。|  
|[ExitAppDomain 方法](icordebugmanagedcallback-exitappdomain-method.md)|通知调试器应用程序域已退出。|  
|[ExitProcess 方法](icordebugmanagedcallback-exitprocess-method.md)|通知调试器进程已退出。|  
|[ExitThread 方法](icordebugmanagedcallback-exitthread-method.md)|通知调试器已退出正在执行的托管代码的线程。|  
|[LoadAssembly 方法](icordebugmanagedcallback-loadassembly-method.md)|通知调试器已成功加载 CLR 程序集。|  
|[LoadClass 方法](icordebugmanagedcallback-loadclass-method.md)|通知调试器已加载某个类。|  
|[LoadModule 方法](icordebugmanagedcallback-loadmodule-method.md)|通知调试器已成功加载 CLR 模块。|  
|[LogMessage 方法](icordebugmanagedcallback-logmessage-method.md)|通知调试器，CLR 托管线程在 <xref:System.Diagnostics.EventLog> 类中调用了方法来记录事件。|  
|[LogSwitch 方法](icordebugmanagedcallback-logswitch-method.md)|通知调试器，CLR 托管线程在 <xref:System.Diagnostics.Switch> 类中调用了方法来创建、修改或删除调试/跟踪开关。|  
|[NameChange 方法](icordebugmanagedcallback-namechange-method.md)|通知调试器应用程序域或线程的名称已更改。|  
|[StepComplete 方法](icordebugmanagedcallback-stepcomplete-method.md)|通知调试器某个步骤已完成。|  
|[UnloadAssembly 方法](icordebugmanagedcallback-unloadassembly-method.md)|通知调试器已卸载 CLR 程序集。|  
|[UnloadClass 方法](icordebugmanagedcallback-unloadclass-method.md)|通知调试器正在卸载某个类。|  
|[UnloadModule 方法](icordebugmanagedcallback-unloadmodule-method.md)|通知调试器已卸载 CLR 模块（DLL）。|  
|[UpdateModuleSymbols 方法](icordebugmanagedcallback-updatemodulesymbols-method.md)|通知调试器 CLR 模块的符号已更改。|  
  
## <a name="remarks"></a>备注  
 所有回调都是序列化的，在同一线程中调用，并在进程处于已同步状态的情况下调用。  
  
 每个回调实现都必须调用[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)以继续执行。 如果在回调返回之前未调用 `ICorDebugController::Continue`，该进程将保持停止状态，并且在调用 `ICorDebugController::Continue` 之前，不会再发生更多的事件回调。  
  
 如果调试程序正在 .NET Framework 版本2.0 应用程序进行调试，则必须实现[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 。 `ICorDebugManagedCallback` 或 `ICorDebugManagedCallback2` 的实例作为回调对象传递到[ICorDebug：： SetManagedHandler](icordebug-setmanagedhandler-method.md)。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebug 接口](icordebug-interface.md)
- [ICorDebugManagedCallback2 接口](icordebugmanagedcallback2-interface.md)
- [调试接口](debugging-interfaces.md)
