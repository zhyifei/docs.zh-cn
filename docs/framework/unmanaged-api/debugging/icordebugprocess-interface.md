---
title: "ICorDebugProcess 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess
helpviewer_keywords: ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ee526a79d89a9e4e3483daa07a512b6b7f920e70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess-interface1"></a><span data-ttu-id="4bc37-102">ICorDebugProcess 接口 1</span><span class="sxs-lookup"><span data-stu-id="4bc37-102">ICorDebugProcess Interface1</span></span>
<span data-ttu-id="4bc37-103">表示正在执行托管代码的进程。</span><span class="sxs-lookup"><span data-stu-id="4bc37-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="4bc37-104">此接口是 ICorDebugController 的子类。</span><span class="sxs-lookup"><span data-stu-id="4bc37-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4bc37-105">方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-105">Methods</span></span>  
  
|<span data-ttu-id="4bc37-106">方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-106">Method</span></span>|<span data-ttu-id="4bc37-107">描述</span><span class="sxs-lookup"><span data-stu-id="4bc37-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4bc37-108">ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="4bc37-109">清除在给定的线程上当前的非托管的异常。</span><span class="sxs-lookup"><span data-stu-id="4bc37-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="4bc37-110">EnableLogMessages 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="4bc37-111">启用和禁用日志消息发送到调试器。</span><span class="sxs-lookup"><span data-stu-id="4bc37-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="4bc37-112">EnumerateAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="4bc37-113">枚举中的所有应用程序域的过程。</span><span class="sxs-lookup"><span data-stu-id="4bc37-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="4bc37-114">EnumerateObjects 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="4bc37-115">未实现。</span><span class="sxs-lookup"><span data-stu-id="4bc37-115">Not implemented.</span></span>|  
|[<span data-ttu-id="4bc37-116">GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="4bc37-117">获取进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="4bc37-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="4bc37-118">GetHelperThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="4bc37-119">获取调试器的内部帮助程序线程的操作系统 (OS) 线程 ID。</span><span class="sxs-lookup"><span data-stu-id="4bc37-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="4bc37-120">GetID 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="4bc37-121">获取进程的操作系统 (OS) ID。</span><span class="sxs-lookup"><span data-stu-id="4bc37-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="4bc37-122">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="4bc37-123">未实现。</span><span class="sxs-lookup"><span data-stu-id="4bc37-123">Not implemented.</span></span>|  
|[<span data-ttu-id="4bc37-124">GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="4bc37-125">获取具有指定的操作系统线程的 ICorDebugThread 实例 id。</span><span class="sxs-lookup"><span data-stu-id="4bc37-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="4bc37-126">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="4bc37-127">获取给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="4bc37-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="4bc37-128">IsOSSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="4bc37-129">确定线程是否已挂起由于调试器停止进程。</span><span class="sxs-lookup"><span data-stu-id="4bc37-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="4bc37-130">IsTransitionStub 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="4bc37-131">确定是否处于存根，将导致向托管代码转换内的地址。</span><span class="sxs-lookup"><span data-stu-id="4bc37-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="4bc37-132">ModifyLogSwitch 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="4bc37-133">设置指定的日志交换机的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="4bc37-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="4bc37-134">ReadMemory 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="4bc37-135">从进程读取内存。</span><span class="sxs-lookup"><span data-stu-id="4bc37-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="4bc37-136">SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="4bc37-137">设置给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="4bc37-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="4bc37-138">ThreadForFiberCookie 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="4bc37-139">已否决。</span><span class="sxs-lookup"><span data-stu-id="4bc37-139">Deprecated.</span></span>|  
|[<span data-ttu-id="4bc37-140">WriteMemory 方法</span><span class="sxs-lookup"><span data-stu-id="4bc37-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="4bc37-141">将数据写入的过程中的内存区域。</span><span class="sxs-lookup"><span data-stu-id="4bc37-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bc37-142">备注</span><span class="sxs-lookup"><span data-stu-id="4bc37-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bc37-143">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4bc37-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bc37-144">要求</span><span class="sxs-lookup"><span data-stu-id="4bc37-144">Requirements</span></span>  
 <span data-ttu-id="4bc37-145">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4bc37-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bc37-146">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bc37-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bc37-147">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bc37-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bc37-148">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bc37-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc37-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bc37-149">See Also</span></span>  
 [<span data-ttu-id="4bc37-150">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="4bc37-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="4bc37-151">调试接口</span><span class="sxs-lookup"><span data-stu-id="4bc37-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
