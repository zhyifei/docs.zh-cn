---
title: "ICorDebugThread 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2df43a35e510695d7af0c38cbb8fb3b051f5f354
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread-interface1"></a><span data-ttu-id="764c9-102">ICorDebugThread 接口 1</span><span class="sxs-lookup"><span data-stu-id="764c9-102">ICorDebugThread Interface1</span></span>
<span data-ttu-id="764c9-103">表示进程中的线程。</span><span class="sxs-lookup"><span data-stu-id="764c9-103">Represents a thread in a process.</span></span> <span data-ttu-id="764c9-104">`ICorDebugThread` 实例的生存期与它表示的线程的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="764c9-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="764c9-105">方法</span><span class="sxs-lookup"><span data-stu-id="764c9-105">Methods</span></span>  
  
|<span data-ttu-id="764c9-106">方法</span><span class="sxs-lookup"><span data-stu-id="764c9-106">Method</span></span>|<span data-ttu-id="764c9-107">描述</span><span class="sxs-lookup"><span data-stu-id="764c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="764c9-108">ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="764c9-109">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="764c9-109">This method is not implemented.</span></span> <span data-ttu-id="764c9-110">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="764c9-110">Do not use it.</span></span>|  
|[<span data-ttu-id="764c9-111">CreateEval 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="764c9-112">在此创建操作的 ICorDebugEval 对象`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-113">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="764c9-114">创建允许逐句通过在此活动帧的 ICorDebugStepper 对象`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-115">EnumerateChains 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="764c9-116">为包含在此的所有堆栈链 ICorDebugChainEnum 枚举器获取的接口指针`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-117">GetActiveChain 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="764c9-118">获取的接口指针到活动 ICorDebugChain 此`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-119">GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="764c9-120">获取的接口指针到活动 ICorDebugFrame 此`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-121">GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="764c9-122">用于应用程序域中获取的接口指针，此`ICorDebugThread`当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="764c9-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="764c9-123">GetCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="764c9-124">获取一个表示当前由托管代码引发的异常的 ICorDebugValue 对象的接口指针。</span><span class="sxs-lookup"><span data-stu-id="764c9-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="764c9-125">GetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="764c9-126">获取描述当前的调试状态的这一个 CorDebugThreadState 值`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-127">GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="764c9-128">获取当前句柄的活动部分`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-129">GetID 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="764c9-130">获取此活动的部分的当前操作系统标识符`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-131">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="764c9-132">获取公共语言运行时 (CLR) 线程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="764c9-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="764c9-133">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="764c9-134">此过程中获取的接口指针`ICorDebugThread`窗体一部分。</span><span class="sxs-lookup"><span data-stu-id="764c9-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="764c9-135">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="764c9-136">获取与此关联的寄存器集的接口指针`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-137">GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="764c9-138">获取描述此的当前状态的 CorDebugUserState 值的按位组合`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="764c9-139">SetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="764c9-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="764c9-140">设置的按位组合`CorDebugThreadState`值，用于描述此的调试状态`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="764c9-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="764c9-141">备注</span><span class="sxs-lookup"><span data-stu-id="764c9-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="764c9-142">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="764c9-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="764c9-143">惠?</span><span class="sxs-lookup"><span data-stu-id="764c9-143">Requirements</span></span>  
 <span data-ttu-id="764c9-144">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="764c9-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="764c9-145">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="764c9-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="764c9-146">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="764c9-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="764c9-147">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="764c9-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="764c9-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="764c9-148">See Also</span></span>  
 [<span data-ttu-id="764c9-149">调试接口</span><span class="sxs-lookup"><span data-stu-id="764c9-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
