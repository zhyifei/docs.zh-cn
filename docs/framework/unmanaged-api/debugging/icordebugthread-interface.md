---
title: ICorDebugThread 接口
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
ms.openlocfilehash: c7333f4210d0a2ec4ff71a0fac0ea00068fecc57
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133500"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="60ccb-102">ICorDebugThread 接口</span><span class="sxs-lookup"><span data-stu-id="60ccb-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="60ccb-103">表示进程中的线程。</span><span class="sxs-lookup"><span data-stu-id="60ccb-103">Represents a thread in a process.</span></span> <span data-ttu-id="60ccb-104">`ICorDebugThread` 实例的生存期与它表示的线程的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="60ccb-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60ccb-105">方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-105">Methods</span></span>  
  
|<span data-ttu-id="60ccb-106">方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-106">Method</span></span>|<span data-ttu-id="60ccb-107">描述</span><span class="sxs-lookup"><span data-stu-id="60ccb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60ccb-108">ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="60ccb-109">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="60ccb-109">This method is not implemented.</span></span> <span data-ttu-id="60ccb-110">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="60ccb-110">Do not use it.</span></span>|  
|[<span data-ttu-id="60ccb-111">CreateEval 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="60ccb-112">创建在此 `ICorDebugThread`上操作的 ICorDebugEval 对象。</span><span class="sxs-lookup"><span data-stu-id="60ccb-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-113">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="60ccb-114">创建一个 ICorDebugStepper 对象，该对象允许单步执行此 `ICorDebugThread`中的活动框架。</span><span class="sxs-lookup"><span data-stu-id="60ccb-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-115">EnumerateChains 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="60ccb-116">获取一个接口指针，该指针指向包含此 `ICorDebugThread`中所有堆栈链的 ICorDebugChainEnum 枚举器。</span><span class="sxs-lookup"><span data-stu-id="60ccb-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-117">GetActiveChain 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="60ccb-118">获取此 `ICorDebugThread`上的活动 ICorDebugChain 的接口指针。</span><span class="sxs-lookup"><span data-stu-id="60ccb-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-119">GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="60ccb-120">获取此 `ICorDebugThread`上的活动 ICorDebugFrame 的接口指针。</span><span class="sxs-lookup"><span data-stu-id="60ccb-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-121">GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="60ccb-122">获取一个接口指针，该指针指向当前在其中执行此 `ICorDebugThread` 的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="60ccb-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="60ccb-123">GetCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="60ccb-124">获取一个指向 ICorDebugValue 对象的接口指针，该对象表示当前由托管代码引发的异常。</span><span class="sxs-lookup"><span data-stu-id="60ccb-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="60ccb-125">GetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="60ccb-126">获取描述此 `ICorDebugThread`当前调试状态的 CorDebugThreadState 值。</span><span class="sxs-lookup"><span data-stu-id="60ccb-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-127">GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="60ccb-128">获取此 `ICorDebugThread`的活动部分的当前句柄。</span><span class="sxs-lookup"><span data-stu-id="60ccb-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-129">GetID 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="60ccb-130">获取此 `ICorDebugThread`的活动部分的当前操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="60ccb-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-131">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="60ccb-132">获取公共语言运行时（CLR）线程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="60ccb-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="60ccb-133">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="60ccb-134">获取一个接口指针，该指针指向此 `ICorDebugThread` 构成部分的进程。</span><span class="sxs-lookup"><span data-stu-id="60ccb-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="60ccb-135">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="60ccb-136">获取一个接口指针，该指针指向与此 `ICorDebugThread`关联的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="60ccb-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-137">GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="60ccb-138">获取 CorDebugUserState 值的按位组合，这些值描述此 `ICorDebugThread`的当前状态。</span><span class="sxs-lookup"><span data-stu-id="60ccb-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="60ccb-139">SetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="60ccb-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="60ccb-140">设置 `CorDebugThreadState` 值的按位组合，这些值描述此 `ICorDebugThread`的调试状态。</span><span class="sxs-lookup"><span data-stu-id="60ccb-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60ccb-141">备注</span><span class="sxs-lookup"><span data-stu-id="60ccb-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="60ccb-142">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="60ccb-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60ccb-143">要求</span><span class="sxs-lookup"><span data-stu-id="60ccb-143">Requirements</span></span>  
 <span data-ttu-id="60ccb-144">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="60ccb-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60ccb-145">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60ccb-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60ccb-146">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60ccb-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60ccb-147">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60ccb-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ccb-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="60ccb-148">See also</span></span>

- [<span data-ttu-id="60ccb-149">调试接口</span><span class="sxs-lookup"><span data-stu-id="60ccb-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
