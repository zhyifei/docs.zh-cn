---
title: ICorDebug 接口
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
ms.openlocfilehash: 0ca66f001d04bc86b64e0fe2d1cd37559e4fc633
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785120"
---
# <a name="icordebug-interface"></a><span data-ttu-id="a03e3-102">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="a03e3-102">ICorDebug Interface</span></span>
<span data-ttu-id="a03e3-103">提供允许开发人员在公共语言运行时（CLR）环境中调试应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="a03e3-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a03e3-104">Windows 95、Windows 98 或 Windows ME 或非 x86 平台（如 IA64 和 AMD64）不支持混合模式（托管和本机代码）调试。</span><span class="sxs-lookup"><span data-stu-id="a03e3-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a03e3-105">方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-105">Methods</span></span>  
  
|<span data-ttu-id="a03e3-106">方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-106">Method</span></span>|<span data-ttu-id="a03e3-107">描述</span><span class="sxs-lookup"><span data-stu-id="a03e3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a03e3-108">CanLaunchOrAttach 方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-108">CanLaunchOrAttach Method</span></span>](icordebug-canlaunchorattach-method.md)|<span data-ttu-id="a03e3-109">确定是否可以在当前计算机和运行时配置的上下文中启动新进程或附加到给定进程。</span><span class="sxs-lookup"><span data-stu-id="a03e3-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="a03e3-110">CreateProcess 方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-110">CreateProcess Method</span></span>](icordebug-createprocess-method.md)|<span data-ttu-id="a03e3-111">在调试器的控制下启动进程及其主线程。</span><span class="sxs-lookup"><span data-stu-id="a03e3-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="a03e3-112">DebugActiveProcess 方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-112">DebugActiveProcess Method</span></span>](icordebug-debugactiveprocess-method.md)|<span data-ttu-id="a03e3-113">将调试器附加到现有进程。</span><span class="sxs-lookup"><span data-stu-id="a03e3-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="a03e3-114">EnumerateProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-114">EnumerateProcesses Method</span></span>](icordebug-enumerateprocesses-method.md)|<span data-ttu-id="a03e3-115">获取正在调试的进程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="a03e3-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="a03e3-116">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-116">GetProcess Method</span></span>](icordebug-getprocess-method.md)|<span data-ttu-id="a03e3-117">返回具有给定进程 ID 的 "ICorDebugProcess" 对象。</span><span class="sxs-lookup"><span data-stu-id="a03e3-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="a03e3-118">Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-118">Initialize Method</span></span>](icordebug-initialize-method.md)|<span data-ttu-id="a03e3-119">初始化 `ICorDebug` 对象。</span><span class="sxs-lookup"><span data-stu-id="a03e3-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="a03e3-120">SetManagedHandler 方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-120">SetManagedHandler Method</span></span>](icordebug-setmanagedhandler-method.md)|<span data-ttu-id="a03e3-121">指定托管事件的事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="a03e3-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="a03e3-122">SetUnmanagedHandler 方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-122">SetUnmanagedHandler Method</span></span>](icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="a03e3-123">指定非托管事件的事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="a03e3-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="a03e3-124">Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="a03e3-124">Terminate Method</span></span>](icordebug-terminate-method.md)|<span data-ttu-id="a03e3-125">终止 `ICorDebug` 的对象。</span><span class="sxs-lookup"><span data-stu-id="a03e3-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a03e3-126">备注</span><span class="sxs-lookup"><span data-stu-id="a03e3-126">Remarks</span></span>  
 <span data-ttu-id="a03e3-127">`ICorDebug` 表示调试器进程的事件处理循环。</span><span class="sxs-lookup"><span data-stu-id="a03e3-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="a03e3-128">调试程序必须等待所有正在调试的进程中的[ICorDebugManagedCallback：： ExitProcess](icordebugmanagedcallback-exitprocess-method.md)回调，然后释放此接口。</span><span class="sxs-lookup"><span data-stu-id="a03e3-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="a03e3-129">`ICorDebug` 对象是用于控制所有进一步托管调试的初始对象。</span><span class="sxs-lookup"><span data-stu-id="a03e3-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="a03e3-130">在 .NET Framework 版本1.0 和1.1 中，此对象是从 COM 创建的 `CoClass` 对象。</span><span class="sxs-lookup"><span data-stu-id="a03e3-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="a03e3-131">在 .NET Framework 版本2.0 中，此对象不再是 `CoClass` 对象。</span><span class="sxs-lookup"><span data-stu-id="a03e3-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="a03e3-132">它必须通过[CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)函数创建，该函数更易于识别。</span><span class="sxs-lookup"><span data-stu-id="a03e3-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="a03e3-133">此新创建函数使客户端可以获取 `ICorDebug`的特定实现，这也会模拟调试 API 的特定版本。</span><span class="sxs-lookup"><span data-stu-id="a03e3-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a03e3-134">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a03e3-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a03e3-135">需求</span><span class="sxs-lookup"><span data-stu-id="a03e3-135">Requirements</span></span>  
 <span data-ttu-id="a03e3-136">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a03e3-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a03e3-137">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a03e3-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a03e3-138">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a03e3-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a03e3-139">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a03e3-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a03e3-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a03e3-140">See also</span></span>

- [<span data-ttu-id="a03e3-141">调试接口</span><span class="sxs-lookup"><span data-stu-id="a03e3-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
