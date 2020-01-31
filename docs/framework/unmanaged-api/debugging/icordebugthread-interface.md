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
ms.openlocfilehash: b227b374021136e78f7f061d235eb18eca5b9515
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791477"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="910b7-102">ICorDebugThread 接口</span><span class="sxs-lookup"><span data-stu-id="910b7-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="910b7-103">表示进程中的线程。</span><span class="sxs-lookup"><span data-stu-id="910b7-103">Represents a thread in a process.</span></span> <span data-ttu-id="910b7-104">`ICorDebugThread` 实例的生存期与它表示的线程的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="910b7-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="910b7-105">方法</span><span class="sxs-lookup"><span data-stu-id="910b7-105">Methods</span></span>  
  
|<span data-ttu-id="910b7-106">方法</span><span class="sxs-lookup"><span data-stu-id="910b7-106">Method</span></span>|<span data-ttu-id="910b7-107">描述</span><span class="sxs-lookup"><span data-stu-id="910b7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="910b7-108">ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-108">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="910b7-109">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="910b7-109">This method is not implemented.</span></span> <span data-ttu-id="910b7-110">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="910b7-110">Do not use it.</span></span>|  
|[<span data-ttu-id="910b7-111">CreateEval 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-111">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="910b7-112">创建在此 `ICorDebugThread`上操作的 ICorDebugEval 对象。</span><span class="sxs-lookup"><span data-stu-id="910b7-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-113">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-113">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="910b7-114">创建一个 ICorDebugStepper 对象，该对象允许单步执行此 `ICorDebugThread`中的活动框架。</span><span class="sxs-lookup"><span data-stu-id="910b7-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-115">EnumerateChains 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-115">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="910b7-116">获取一个接口指针，该指针指向包含此 `ICorDebugThread`中所有堆栈链的 ICorDebugChainEnum 枚举器。</span><span class="sxs-lookup"><span data-stu-id="910b7-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-117">GetActiveChain 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-117">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="910b7-118">获取此 `ICorDebugThread`上的活动 ICorDebugChain 的接口指针。</span><span class="sxs-lookup"><span data-stu-id="910b7-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-119">GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-119">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="910b7-120">获取此 `ICorDebugThread`上的活动 ICorDebugFrame 的接口指针。</span><span class="sxs-lookup"><span data-stu-id="910b7-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-121">GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-121">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="910b7-122">获取一个接口指针，该指针指向当前在其中执行此 `ICorDebugThread` 的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="910b7-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="910b7-123">GetCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-123">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="910b7-124">获取一个指向 ICorDebugValue 对象的接口指针，该对象表示当前由托管代码引发的异常。</span><span class="sxs-lookup"><span data-stu-id="910b7-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="910b7-125">GetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-125">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="910b7-126">获取描述此 `ICorDebugThread`当前调试状态的 CorDebugThreadState 值。</span><span class="sxs-lookup"><span data-stu-id="910b7-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-127">GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-127">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="910b7-128">获取此 `ICorDebugThread`的活动部分的当前句柄。</span><span class="sxs-lookup"><span data-stu-id="910b7-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-129">GetID 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-129">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="910b7-130">获取此 `ICorDebugThread`的活动部分的当前操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="910b7-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-131">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-131">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="910b7-132">获取公共语言运行时（CLR）线程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="910b7-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="910b7-133">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-133">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="910b7-134">获取一个接口指针，该指针指向此 `ICorDebugThread` 构成部分的进程。</span><span class="sxs-lookup"><span data-stu-id="910b7-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="910b7-135">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-135">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="910b7-136">获取一个接口指针，该指针指向与此 `ICorDebugThread`关联的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="910b7-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-137">GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-137">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="910b7-138">获取 CorDebugUserState 值的按位组合，这些值描述此 `ICorDebugThread`的当前状态。</span><span class="sxs-lookup"><span data-stu-id="910b7-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="910b7-139">SetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="910b7-139">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="910b7-140">设置 `CorDebugThreadState` 值的按位组合，这些值描述此 `ICorDebugThread`的调试状态。</span><span class="sxs-lookup"><span data-stu-id="910b7-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="910b7-141">备注</span><span class="sxs-lookup"><span data-stu-id="910b7-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="910b7-142">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="910b7-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="910b7-143">需求</span><span class="sxs-lookup"><span data-stu-id="910b7-143">Requirements</span></span>  
 <span data-ttu-id="910b7-144">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="910b7-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="910b7-145">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="910b7-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="910b7-146">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="910b7-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="910b7-147">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="910b7-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910b7-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="910b7-148">See also</span></span>

- [<span data-ttu-id="910b7-149">调试接口</span><span class="sxs-lookup"><span data-stu-id="910b7-149">Debugging Interfaces</span></span>](debugging-interfaces.md)
