---
title: ICorDebugStepper 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f83b9796bb692ce234a03c596387960bd879ebf3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212513"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="70754-102">ICorDebugStepper 接口</span><span class="sxs-lookup"><span data-stu-id="70754-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="70754-103">表示在代码执行过程中由调试器执行的一个步骤。此步骤作为命令颁发和完成之间的标识符使用，可以实现取消对某个步骤的执行。</span><span class="sxs-lookup"><span data-stu-id="70754-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70754-104">方法</span><span class="sxs-lookup"><span data-stu-id="70754-104">Methods</span></span>  
  
|<span data-ttu-id="70754-105">方法</span><span class="sxs-lookup"><span data-stu-id="70754-105">Method</span></span>|<span data-ttu-id="70754-106">描述</span><span class="sxs-lookup"><span data-stu-id="70754-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70754-107">Deactivate 方法</span><span class="sxs-lookup"><span data-stu-id="70754-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="70754-108">这将导致`ICorDebugStepper`取消它收到的最后一个步骤命令。</span><span class="sxs-lookup"><span data-stu-id="70754-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="70754-109">IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="70754-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="70754-110">获取一个值，该值指示是否此`ICorDebugStepper`当前正在执行一个步骤。</span><span class="sxs-lookup"><span data-stu-id="70754-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="70754-111">SetInterceptMask 方法</span><span class="sxs-lookup"><span data-stu-id="70754-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="70754-112">设置一个 CorDebugIntercept 值，指定的单步执行代码的类型。</span><span class="sxs-lookup"><span data-stu-id="70754-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="70754-113">SetRangeIL 方法</span><span class="sxs-lookup"><span data-stu-id="70754-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="70754-114">设置一个值，该值指示是否调用[icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)传递参数值相对于本机代码或单步执行方法的 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="70754-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="70754-115">SetUnmappedStopMask 方法</span><span class="sxs-lookup"><span data-stu-id="70754-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="70754-116">设置 CorDebugUnmappedStop 值，该值指定在其中执行都将停止的代码未映射的类型。</span><span class="sxs-lookup"><span data-stu-id="70754-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="70754-117">Step 方法</span><span class="sxs-lookup"><span data-stu-id="70754-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="70754-118">这将导致`ICorDebugStepper`单步执行其包含的线程，并 （可选） 到继续单步执行通过该线程中调用的函数。</span><span class="sxs-lookup"><span data-stu-id="70754-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="70754-119">StepOut 方法</span><span class="sxs-lookup"><span data-stu-id="70754-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="70754-120">这将导致`ICorDebugStepper`单步执行其包含的线程，并完成时的当前帧将控制权返回给调用的帧。</span><span class="sxs-lookup"><span data-stu-id="70754-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="70754-121">StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="70754-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="70754-122">这将导致`ICorDebugStepper`单步执行其包含的线程，并返回时达到超出指定范围的最后一个代码。</span><span class="sxs-lookup"><span data-stu-id="70754-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70754-123">备注</span><span class="sxs-lookup"><span data-stu-id="70754-123">Remarks</span></span>  
 <span data-ttu-id="70754-124">`ICorDebugStepper`接口具有以下用途：</span><span class="sxs-lookup"><span data-stu-id="70754-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="70754-125">它充当颁发步骤命令和命令的完成之间的标识符。</span><span class="sxs-lookup"><span data-stu-id="70754-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="70754-126">它提供了一个中央的界面来封装所有单步执行可执行。</span><span class="sxs-lookup"><span data-stu-id="70754-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="70754-127">它提供了过早地取消单步执行操作的方法。</span><span class="sxs-lookup"><span data-stu-id="70754-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="70754-128">可以有多个分档器每个线程。</span><span class="sxs-lookup"><span data-stu-id="70754-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="70754-129">例如，可能会命中的断点时逐过程执行函数，而用户可能想要启动新的单步执行操作，在该函数内部。</span><span class="sxs-lookup"><span data-stu-id="70754-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="70754-130">负责调试器来确定如何处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="70754-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="70754-131">调试器可能想要取消原始单步执行操作或嵌套两个操作。</span><span class="sxs-lookup"><span data-stu-id="70754-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="70754-132">`ICorDebugStepper`接口支持这两种选择。</span><span class="sxs-lookup"><span data-stu-id="70754-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="70754-133">如果公共语言运行时 (CLR) 进行跨线程的封送调用，分档器可能会在线程间迁移。</span><span class="sxs-lookup"><span data-stu-id="70754-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70754-134">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="70754-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70754-135">要求</span><span class="sxs-lookup"><span data-stu-id="70754-135">Requirements</span></span>  
 <span data-ttu-id="70754-136">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70754-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70754-137">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70754-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70754-138">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70754-138">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="70754-139">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="70754-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="70754-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="70754-140">See also</span></span>

- [<span data-ttu-id="70754-141">调试接口</span><span class="sxs-lookup"><span data-stu-id="70754-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
