---
title: ICorDebugProcess 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46d96d66f16cd956d8fab1afe00486d564e37953
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216790"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="40155-102">ICorDebugProcess 接口</span><span class="sxs-lookup"><span data-stu-id="40155-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="40155-103">表示正在执行托管代码的进程。</span><span class="sxs-lookup"><span data-stu-id="40155-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="40155-104">此接口是 ICorDebugController 的子类。</span><span class="sxs-lookup"><span data-stu-id="40155-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40155-105">方法</span><span class="sxs-lookup"><span data-stu-id="40155-105">Methods</span></span>  
  
|<span data-ttu-id="40155-106">方法</span><span class="sxs-lookup"><span data-stu-id="40155-106">Method</span></span>|<span data-ttu-id="40155-107">描述</span><span class="sxs-lookup"><span data-stu-id="40155-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40155-108">ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="40155-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="40155-109">清除给定线程上当前的非托管的异常。</span><span class="sxs-lookup"><span data-stu-id="40155-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="40155-110">EnableLogMessages 方法</span><span class="sxs-lookup"><span data-stu-id="40155-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="40155-111">启用和禁用日志消息发送到调试器。</span><span class="sxs-lookup"><span data-stu-id="40155-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="40155-112">EnumerateAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="40155-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="40155-113">枚举的所有过程中应用程序域。</span><span class="sxs-lookup"><span data-stu-id="40155-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="40155-114">EnumerateObjects 方法</span><span class="sxs-lookup"><span data-stu-id="40155-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="40155-115">未实现。</span><span class="sxs-lookup"><span data-stu-id="40155-115">Not implemented.</span></span>|  
|[<span data-ttu-id="40155-116">GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="40155-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="40155-117">获取进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="40155-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="40155-118">GetHelperThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="40155-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="40155-119">获取调试器的内部帮助器线程的操作系统 (OS) 线程 ID。</span><span class="sxs-lookup"><span data-stu-id="40155-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="40155-120">GetID 方法</span><span class="sxs-lookup"><span data-stu-id="40155-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="40155-121">获取进程的操作系统 (OS) ID。</span><span class="sxs-lookup"><span data-stu-id="40155-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="40155-122">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="40155-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="40155-123">未实现。</span><span class="sxs-lookup"><span data-stu-id="40155-123">Not implemented.</span></span>|  
|[<span data-ttu-id="40155-124">GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="40155-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="40155-125">获取具有指定的 OS 线程 ICorDebugThread 实例 id。</span><span class="sxs-lookup"><span data-stu-id="40155-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="40155-126">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="40155-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="40155-127">获取给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="40155-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="40155-128">IsOSSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="40155-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="40155-129">确定是否已因调试器停止的进程而挂起线程。</span><span class="sxs-lookup"><span data-stu-id="40155-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="40155-130">IsTransitionStub 方法</span><span class="sxs-lookup"><span data-stu-id="40155-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="40155-131">确定地址是否会导致转换为托管代码的存根内。</span><span class="sxs-lookup"><span data-stu-id="40155-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="40155-132">ModifyLogSwitch 方法</span><span class="sxs-lookup"><span data-stu-id="40155-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="40155-133">设置指定的日志开关的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="40155-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="40155-134">ReadMemory 方法</span><span class="sxs-lookup"><span data-stu-id="40155-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="40155-135">从进程读取内存。</span><span class="sxs-lookup"><span data-stu-id="40155-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="40155-136">SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="40155-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="40155-137">设置给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="40155-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="40155-138">ThreadForFiberCookie 方法</span><span class="sxs-lookup"><span data-stu-id="40155-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="40155-139">已否决。</span><span class="sxs-lookup"><span data-stu-id="40155-139">Deprecated.</span></span>|  
|[<span data-ttu-id="40155-140">WriteMemory 方法</span><span class="sxs-lookup"><span data-stu-id="40155-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="40155-141">将数据写入到的进程中的内存区域。</span><span class="sxs-lookup"><span data-stu-id="40155-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40155-142">备注</span><span class="sxs-lookup"><span data-stu-id="40155-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40155-143">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="40155-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40155-144">要求</span><span class="sxs-lookup"><span data-stu-id="40155-144">Requirements</span></span>  
 <span data-ttu-id="40155-145">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40155-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40155-146">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40155-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40155-147">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40155-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40155-148">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40155-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40155-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="40155-149">See also</span></span>

- [<span data-ttu-id="40155-150">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="40155-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="40155-151">调试接口</span><span class="sxs-lookup"><span data-stu-id="40155-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
