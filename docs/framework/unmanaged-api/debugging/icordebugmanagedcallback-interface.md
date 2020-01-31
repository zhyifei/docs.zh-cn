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
# <a name="icordebugmanagedcallback-interface"></a><span data-ttu-id="23847-102">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="23847-102">ICorDebugManagedCallback Interface</span></span>
<span data-ttu-id="23847-103">提供用于处理调试器回调的方法。</span><span class="sxs-lookup"><span data-stu-id="23847-103">Provides methods to process debugger callbacks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23847-104">方法</span><span class="sxs-lookup"><span data-stu-id="23847-104">Methods</span></span>  
  
|<span data-ttu-id="23847-105">方法</span><span class="sxs-lookup"><span data-stu-id="23847-105">Method</span></span>|<span data-ttu-id="23847-106">描述</span><span class="sxs-lookup"><span data-stu-id="23847-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23847-107">Break 方法</span><span class="sxs-lookup"><span data-stu-id="23847-107">Break Method</span></span>](icordebugmanagedcallback-break-method.md)|<span data-ttu-id="23847-108">当执行代码流中的 <xref:System.Reflection.Emit.OpCodes.Break> 指令时，通知调试器。</span><span class="sxs-lookup"><span data-stu-id="23847-108">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>|  
|[<span data-ttu-id="23847-109">Breakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="23847-109">Breakpoint Method</span></span>](icordebugmanagedcallback-breakpoint-method.md)|<span data-ttu-id="23847-110">遇到断点时，通知调试器。</span><span class="sxs-lookup"><span data-stu-id="23847-110">Notifies the debugger when a breakpoint is encountered.</span></span>|  
|[<span data-ttu-id="23847-111">BreakpointSetError 方法</span><span class="sxs-lookup"><span data-stu-id="23847-111">BreakpointSetError Method</span></span>](icordebugmanagedcallback-breakpointseterror-method.md)|<span data-ttu-id="23847-112">通知调试器，公共语言运行时（CLR）无法准确绑定在实时（JIT）编译函数之前设置的断点。</span><span class="sxs-lookup"><span data-stu-id="23847-112">Notifies the debugger that the common language runtime (CLR) was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>|  
|[<span data-ttu-id="23847-113">ControlCTrap 方法</span><span class="sxs-lookup"><span data-stu-id="23847-113">ControlCTrap Method</span></span>](icordebugmanagedcallback-controlctrap-method.md)|<span data-ttu-id="23847-114">通知调试器在被调试的进程中捕获了 CTRL + C。</span><span class="sxs-lookup"><span data-stu-id="23847-114">Notifies the debugger that a CTRL+C is trapped in the process being debugged.</span></span>|  
|[<span data-ttu-id="23847-115">CreateAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="23847-115">CreateAppDomain Method</span></span>](icordebugmanagedcallback-createappdomain-method.md)|<span data-ttu-id="23847-116">通知调试器已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="23847-116">Notifies the debugger that an application domain has been created.</span></span>|  
|[<span data-ttu-id="23847-117">CreateProcess 方法</span><span class="sxs-lookup"><span data-stu-id="23847-117">CreateProcess Method</span></span>](icordebugmanagedcallback-createprocess-method.md)|<span data-ttu-id="23847-118">第一次附加或启动进程时，通知调试器。</span><span class="sxs-lookup"><span data-stu-id="23847-118">Notifies the debugger when a process has been attached or started for the first time.</span></span>|  
|[<span data-ttu-id="23847-119">CreateThread 方法</span><span class="sxs-lookup"><span data-stu-id="23847-119">CreateThread Method</span></span>](icordebugmanagedcallback-createthread-method.md)|<span data-ttu-id="23847-120">通知调试器线程已开始执行托管代码。</span><span class="sxs-lookup"><span data-stu-id="23847-120">Notifies the debugger that a thread has started executing managed code.</span></span>|  
|[<span data-ttu-id="23847-121">DebuggerError 方法</span><span class="sxs-lookup"><span data-stu-id="23847-121">DebuggerError Method</span></span>](icordebugmanagedcallback-debuggererror-method.md)|<span data-ttu-id="23847-122">通知调试器在尝试处理来自 CLR 的事件时出错。</span><span class="sxs-lookup"><span data-stu-id="23847-122">Notifies the debugger that an error has occurred while attempting to handle an event from the CLR.</span></span>|  
|[<span data-ttu-id="23847-123">EditAndContinueRemap 方法</span><span class="sxs-lookup"><span data-stu-id="23847-123">EditAndContinueRemap Method</span></span>](icordebugmanagedcallback-editandcontinueremap-method.md)|<span data-ttu-id="23847-124">已否决。</span><span class="sxs-lookup"><span data-stu-id="23847-124">Deprecated.</span></span> <span data-ttu-id="23847-125">通知调试器已将重新映射事件发送到 IDE。</span><span class="sxs-lookup"><span data-stu-id="23847-125">Notifies the debugger that a remap event has been sent to the IDE.</span></span>|  
|[<span data-ttu-id="23847-126">EvalComplete 方法</span><span class="sxs-lookup"><span data-stu-id="23847-126">EvalComplete Method</span></span>](icordebugmanagedcallback-evalcomplete-method.md)|<span data-ttu-id="23847-127">通知调试器已完成计算。</span><span class="sxs-lookup"><span data-stu-id="23847-127">Notifies the debugger that an evaluation has been completed.</span></span>|  
|[<span data-ttu-id="23847-128">EvalException 方法</span><span class="sxs-lookup"><span data-stu-id="23847-128">EvalException Method</span></span>](icordebugmanagedcallback-evalexception-method.md)|<span data-ttu-id="23847-129">通知调试器由于未处理的异常而终止了计算。</span><span class="sxs-lookup"><span data-stu-id="23847-129">Notifies the debugger that an evaluation has been terminated with an unhandled exception.</span></span>|  
|[<span data-ttu-id="23847-130">Exception 方法</span><span class="sxs-lookup"><span data-stu-id="23847-130">Exception Method</span></span>](icordebugmanagedcallback-exception-method.md)|<span data-ttu-id="23847-131">通知调试器已从托管代码引发了异常。</span><span class="sxs-lookup"><span data-stu-id="23847-131">Notifies the debugger that an exception has been thrown from managed code.</span></span>|  
|[<span data-ttu-id="23847-132">ExitAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="23847-132">ExitAppDomain Method</span></span>](icordebugmanagedcallback-exitappdomain-method.md)|<span data-ttu-id="23847-133">通知调试器应用程序域已退出。</span><span class="sxs-lookup"><span data-stu-id="23847-133">Notifies the debugger that an application domain has exited.</span></span>|  
|[<span data-ttu-id="23847-134">ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="23847-134">ExitProcess Method</span></span>](icordebugmanagedcallback-exitprocess-method.md)|<span data-ttu-id="23847-135">通知调试器进程已退出。</span><span class="sxs-lookup"><span data-stu-id="23847-135">Notifies the debugger that a process has exited.</span></span>|  
|[<span data-ttu-id="23847-136">ExitThread 方法</span><span class="sxs-lookup"><span data-stu-id="23847-136">ExitThread Method</span></span>](icordebugmanagedcallback-exitthread-method.md)|<span data-ttu-id="23847-137">通知调试器已退出正在执行的托管代码的线程。</span><span class="sxs-lookup"><span data-stu-id="23847-137">Notifies the debugger that a thread that was executing managed code has exited.</span></span>|  
|[<span data-ttu-id="23847-138">LoadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="23847-138">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)|<span data-ttu-id="23847-139">通知调试器已成功加载 CLR 程序集。</span><span class="sxs-lookup"><span data-stu-id="23847-139">Notifies the debugger that a CLR assembly has been successfully loaded.</span></span>|  
|[<span data-ttu-id="23847-140">LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="23847-140">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)|<span data-ttu-id="23847-141">通知调试器已加载某个类。</span><span class="sxs-lookup"><span data-stu-id="23847-141">Notifies the debugger that a class has been loaded.</span></span>|  
|[<span data-ttu-id="23847-142">LoadModule 方法</span><span class="sxs-lookup"><span data-stu-id="23847-142">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)|<span data-ttu-id="23847-143">通知调试器已成功加载 CLR 模块。</span><span class="sxs-lookup"><span data-stu-id="23847-143">Notifies the debugger that a CLR module has been successfully loaded.</span></span>|  
|[<span data-ttu-id="23847-144">LogMessage 方法</span><span class="sxs-lookup"><span data-stu-id="23847-144">LogMessage Method</span></span>](icordebugmanagedcallback-logmessage-method.md)|<span data-ttu-id="23847-145">通知调试器，CLR 托管线程在 <xref:System.Diagnostics.EventLog> 类中调用了方法来记录事件。</span><span class="sxs-lookup"><span data-stu-id="23847-145">Notifies the debugger that a CLR managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>|  
|[<span data-ttu-id="23847-146">LogSwitch 方法</span><span class="sxs-lookup"><span data-stu-id="23847-146">LogSwitch Method</span></span>](icordebugmanagedcallback-logswitch-method.md)|<span data-ttu-id="23847-147">通知调试器，CLR 托管线程在 <xref:System.Diagnostics.Switch> 类中调用了方法来创建、修改或删除调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="23847-147">Notifies the debugger that a CLR managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>|  
|[<span data-ttu-id="23847-148">NameChange 方法</span><span class="sxs-lookup"><span data-stu-id="23847-148">NameChange Method</span></span>](icordebugmanagedcallback-namechange-method.md)|<span data-ttu-id="23847-149">通知调试器应用程序域或线程的名称已更改。</span><span class="sxs-lookup"><span data-stu-id="23847-149">Notifies the debugger that the name of either an application domain or thread has changed.</span></span>|  
|[<span data-ttu-id="23847-150">StepComplete 方法</span><span class="sxs-lookup"><span data-stu-id="23847-150">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)|<span data-ttu-id="23847-151">通知调试器某个步骤已完成。</span><span class="sxs-lookup"><span data-stu-id="23847-151">Notifies the debugger that a step has completed.</span></span>|  
|[<span data-ttu-id="23847-152">UnloadAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="23847-152">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)|<span data-ttu-id="23847-153">通知调试器已卸载 CLR 程序集。</span><span class="sxs-lookup"><span data-stu-id="23847-153">Notifies the debugger that a CLR assembly has been unloaded.</span></span>|  
|[<span data-ttu-id="23847-154">UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="23847-154">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)|<span data-ttu-id="23847-155">通知调试器正在卸载某个类。</span><span class="sxs-lookup"><span data-stu-id="23847-155">Notifies the debugger that a class is being unloaded.</span></span>|  
|[<span data-ttu-id="23847-156">UnloadModule 方法</span><span class="sxs-lookup"><span data-stu-id="23847-156">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)|<span data-ttu-id="23847-157">通知调试器已卸载 CLR 模块（DLL）。</span><span class="sxs-lookup"><span data-stu-id="23847-157">Notifies the debugger that a CLR module (DLL) has been unloaded.</span></span>|  
|[<span data-ttu-id="23847-158">UpdateModuleSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="23847-158">UpdateModuleSymbols Method</span></span>](icordebugmanagedcallback-updatemodulesymbols-method.md)|<span data-ttu-id="23847-159">通知调试器 CLR 模块的符号已更改。</span><span class="sxs-lookup"><span data-stu-id="23847-159">Notifies the debugger that the symbols for a CLR module have changed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23847-160">备注</span><span class="sxs-lookup"><span data-stu-id="23847-160">Remarks</span></span>  
 <span data-ttu-id="23847-161">所有回调都是序列化的，在同一线程中调用，并在进程处于已同步状态的情况下调用。</span><span class="sxs-lookup"><span data-stu-id="23847-161">All callbacks are serialized, called in the same thread, and called with the process in the synchronized state.</span></span>  
  
 <span data-ttu-id="23847-162">每个回调实现都必须调用[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)以继续执行。</span><span class="sxs-lookup"><span data-stu-id="23847-162">Each callback implementation must call [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to resume execution.</span></span> <span data-ttu-id="23847-163">如果在回调返回之前未调用 `ICorDebugController::Continue`，该进程将保持停止状态，并且在调用 `ICorDebugController::Continue` 之前，不会再发生更多的事件回调。</span><span class="sxs-lookup"><span data-stu-id="23847-163">If `ICorDebugController::Continue` is not called before the callback returns, the process will remain stopped and no more event callbacks will occur until `ICorDebugController::Continue` is called.</span></span>  
  
 <span data-ttu-id="23847-164">如果调试程序正在 .NET Framework 版本2.0 应用程序进行调试，则必须实现[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="23847-164">A debugger must implement [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) if it is debugging .NET Framework version 2.0 applications.</span></span> <span data-ttu-id="23847-165">`ICorDebugManagedCallback` 或 `ICorDebugManagedCallback2` 的实例作为回调对象传递到[ICorDebug：： SetManagedHandler](icordebug-setmanagedhandler-method.md)。</span><span class="sxs-lookup"><span data-stu-id="23847-165">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23847-166">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="23847-166">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23847-167">需求</span><span class="sxs-lookup"><span data-stu-id="23847-167">Requirements</span></span>  
 <span data-ttu-id="23847-168">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23847-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23847-169">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23847-169">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23847-170">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23847-170">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23847-171">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23847-171">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23847-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23847-172">See also</span></span>

- [<span data-ttu-id="23847-173">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="23847-173">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="23847-174">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="23847-174">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="23847-175">调试接口</span><span class="sxs-lookup"><span data-stu-id="23847-175">Debugging Interfaces</span></span>](debugging-interfaces.md)
