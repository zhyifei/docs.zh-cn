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
ms.openlocfilehash: ab48efccc88787f099a182627777db95304cdc3e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212069"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="816ff-102">ICorDebugProcess 接口</span><span class="sxs-lookup"><span data-stu-id="816ff-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="816ff-103">表示正在执行托管代码的进程。</span><span class="sxs-lookup"><span data-stu-id="816ff-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="816ff-104">此接口是 ICorDebugController 的子类。</span><span class="sxs-lookup"><span data-stu-id="816ff-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="816ff-105">方法</span><span class="sxs-lookup"><span data-stu-id="816ff-105">Methods</span></span>  
  
|<span data-ttu-id="816ff-106">方法</span><span class="sxs-lookup"><span data-stu-id="816ff-106">Method</span></span>|<span data-ttu-id="816ff-107">描述</span><span class="sxs-lookup"><span data-stu-id="816ff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="816ff-108">ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="816ff-109">清除给定线程上的当前非托管异常。</span><span class="sxs-lookup"><span data-stu-id="816ff-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="816ff-110">EnableLogMessages 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="816ff-111">启用和禁用向调试器发送日志消息。</span><span class="sxs-lookup"><span data-stu-id="816ff-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="816ff-112">EnumerateAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="816ff-113">枚举进程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="816ff-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="816ff-114">EnumerateObjects 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="816ff-115">未实现。</span><span class="sxs-lookup"><span data-stu-id="816ff-115">Not implemented.</span></span>|  
|[<span data-ttu-id="816ff-116">GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="816ff-117">获取进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="816ff-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="816ff-118">GetHelperThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="816ff-119">获取调试器的内部帮助器线程的操作系统（OS）线程 ID。</span><span class="sxs-lookup"><span data-stu-id="816ff-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="816ff-120">GetID 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="816ff-121">获取进程的操作系统（OS） ID。</span><span class="sxs-lookup"><span data-stu-id="816ff-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="816ff-122">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="816ff-123">未实现。</span><span class="sxs-lookup"><span data-stu-id="816ff-123">Not implemented.</span></span>|  
|[<span data-ttu-id="816ff-124">GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="816ff-125">获取具有指定 OS 线程 ID 的 ICorDebugThread 实例。</span><span class="sxs-lookup"><span data-stu-id="816ff-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="816ff-126">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="816ff-127">获取给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="816ff-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="816ff-128">IsOSSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="816ff-129">确定线程是否由于调试器停止进程而挂起。</span><span class="sxs-lookup"><span data-stu-id="816ff-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="816ff-130">IsTransitionStub 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="816ff-131">确定地址是否在将导致转换到托管代码的存根内。</span><span class="sxs-lookup"><span data-stu-id="816ff-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="816ff-132">ModifyLogSwitch 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="816ff-133">设置指定的日志开关的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="816ff-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="816ff-134">ReadMemory 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="816ff-135">从进程读取内存。</span><span class="sxs-lookup"><span data-stu-id="816ff-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="816ff-136">SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="816ff-137">设置给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="816ff-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="816ff-138">ThreadForFiberCookie 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="816ff-139">已弃用。</span><span class="sxs-lookup"><span data-stu-id="816ff-139">Deprecated.</span></span>|  
|[<span data-ttu-id="816ff-140">WriteMemory 方法</span><span class="sxs-lookup"><span data-stu-id="816ff-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="816ff-141">将数据写入进程中的内存区域。</span><span class="sxs-lookup"><span data-stu-id="816ff-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="816ff-142">备注</span><span class="sxs-lookup"><span data-stu-id="816ff-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="816ff-143">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="816ff-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="816ff-144">要求</span><span class="sxs-lookup"><span data-stu-id="816ff-144">Requirements</span></span>  
 <span data-ttu-id="816ff-145">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="816ff-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="816ff-146">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="816ff-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="816ff-147">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="816ff-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="816ff-148">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="816ff-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="816ff-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="816ff-149">See also</span></span>

- [<span data-ttu-id="816ff-150">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="816ff-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="816ff-151">调试接口</span><span class="sxs-lookup"><span data-stu-id="816ff-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
