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
ms.openlocfilehash: cb52150a17c9ec8f4bbc25c13b85bce56b221eeb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791191"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="7be6b-102">ICorDebugUnmanagedCallback::DebugEvent 方法</span><span class="sxs-lookup"><span data-stu-id="7be6b-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="7be6b-103">通知调试器已激发本机事件。</span><span class="sxs-lookup"><span data-stu-id="7be6b-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be6b-104">语法</span><span class="sxs-lookup"><span data-stu-id="7be6b-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7be6b-105">参数</span><span class="sxs-lookup"><span data-stu-id="7be6b-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="7be6b-106">中指向本机事件的指针。</span><span class="sxs-lookup"><span data-stu-id="7be6b-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="7be6b-107">[in] `true`，如果在非托管事件发生后无法与托管进程状态交互，则在调试器调用[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)之前，否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="7be6b-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7be6b-108">备注</span><span class="sxs-lookup"><span data-stu-id="7be6b-108">Remarks</span></span>  
 <span data-ttu-id="7be6b-109">如果正在调试的线程是 Win32 线程，请不要使用 Win32 调试接口的任何成员。</span><span class="sxs-lookup"><span data-stu-id="7be6b-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="7be6b-110">只能在 Win32 线程上调用 `ICorDebugController::Continue`，且仅当在带外事件继续时才调用。</span><span class="sxs-lookup"><span data-stu-id="7be6b-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="7be6b-111">`DebugEvent` 回调不遵循用于回调的标准规则。</span><span class="sxs-lookup"><span data-stu-id="7be6b-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="7be6b-112">调用 `DebugEvent`时，该进程将处于原始的 OS 调试停止状态。</span><span class="sxs-lookup"><span data-stu-id="7be6b-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="7be6b-113">将不同步该进程。</span><span class="sxs-lookup"><span data-stu-id="7be6b-113">The process will not be synchronized.</span></span> <span data-ttu-id="7be6b-114">它将在必要时自动进入 "已同步" 状态以满足有关托管代码的信息请求，这可能会导致其他嵌套 `DebugEvent` 回调。</span><span class="sxs-lookup"><span data-stu-id="7be6b-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="7be6b-115">在进程上调用[ICorDebugProcess：： ClearCurrentException](icordebugprocess-clearcurrentexception-method.md) ，以忽略异常事件，然后继续此过程。</span><span class="sxs-lookup"><span data-stu-id="7be6b-115">Call [ICorDebugProcess::ClearCurrentException](icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="7be6b-116">调用此方法会在 CONTINUE 请求上发送 DBG_CONTINUE，而不是 DBG_EXCEPTION_NOT_HANDLED，并自动清除带外断点和单步例外。</span><span class="sxs-lookup"><span data-stu-id="7be6b-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="7be6b-117">即使在要调试的应用程序出现停止和已有的带内事件已存在时，也可以随时发出带外事件。</span><span class="sxs-lookup"><span data-stu-id="7be6b-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="7be6b-118">在 .NET Framework 版本2.0 中，调试程序应立即继续越过带外断点事件。</span><span class="sxs-lookup"><span data-stu-id="7be6b-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="7be6b-119">调试器应使用[ICorDebugProcess2：： SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)和[ICorDebugProcess2：： ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md)方法添加和移除断点。</span><span class="sxs-lookup"><span data-stu-id="7be6b-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="7be6b-120">这些方法将自动跳过任何带外断点。</span><span class="sxs-lookup"><span data-stu-id="7be6b-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="7be6b-121">因此，调度的唯一的带外断点应该是已在指令流中的原始断点，如调用 Win32 `DebugBreak` 函数。</span><span class="sxs-lookup"><span data-stu-id="7be6b-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="7be6b-122">请勿尝试使用 `ICorDebugProcess::ClearCurrentException`、 [ICorDebugProcess：： GetThreadContext](icordebugprocess-getthreadcontext-method.md)、 [ICorDebugProcess：： SETTHREADCONTEXT](icordebugprocess-setthreadcontext-method.md)或[调试 API](index.md)的任何其他成员。</span><span class="sxs-lookup"><span data-stu-id="7be6b-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be6b-123">需求</span><span class="sxs-lookup"><span data-stu-id="7be6b-123">Requirements</span></span>  
 <span data-ttu-id="7be6b-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7be6b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be6b-125">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7be6b-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7be6b-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7be6b-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7be6b-127">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be6b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be6b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7be6b-128">See also</span></span>

- [<span data-ttu-id="7be6b-129">ICorDebugUnmanagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="7be6b-129">ICorDebugUnmanagedCallback Interface</span></span>](icordebugunmanagedcallback-interface.md)
