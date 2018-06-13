---
title: ICorDebugStepper 接口 1
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
ms.openlocfilehash: 339b823e5e9f38ffd175c79e379e28ccc3565c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423281"
---
# <a name="icordebugstepper-interface1"></a><span data-ttu-id="ffa86-102">ICorDebugStepper 接口 1</span><span class="sxs-lookup"><span data-stu-id="ffa86-102">ICorDebugStepper Interface1</span></span>
<span data-ttu-id="ffa86-103">表示在代码执行过程中由调试器执行的一个步骤。此步骤作为命令颁发和完成之间的标识符使用，可以实现取消对某个步骤的执行。</span><span class="sxs-lookup"><span data-stu-id="ffa86-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffa86-104">方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-104">Methods</span></span>  
  
|<span data-ttu-id="ffa86-105">方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-105">Method</span></span>|<span data-ttu-id="ffa86-106">描述</span><span class="sxs-lookup"><span data-stu-id="ffa86-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffa86-107">Deactivate 方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="ffa86-108">这将导致`ICorDebugStepper`取消它收到的最后一个步骤命令。</span><span class="sxs-lookup"><span data-stu-id="ffa86-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="ffa86-109">IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="ffa86-110">获取一个值，该值指示是否这`ICorDebugStepper`当前正在执行一个步骤。</span><span class="sxs-lookup"><span data-stu-id="ffa86-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="ffa86-111">SetInterceptMask 方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="ffa86-112">设置一个 CorDebugIntercept 值，指定的单步执行代码的类型。</span><span class="sxs-lookup"><span data-stu-id="ffa86-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="ffa86-113">SetRangeIL 方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="ffa86-114">设置一个值，该值指示是否调用[icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)传递自变量值相对于本机代码或单步执行的方法的 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="ffa86-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="ffa86-115">SetUnmappedStopMask 方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="ffa86-116">设置一个 CorDebugUnmappedStop 值，指定的顺序，则执行将暂停的非托管代码的类型。</span><span class="sxs-lookup"><span data-stu-id="ffa86-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="ffa86-117">Step 方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="ffa86-118">这将导致`ICorDebugStepper`到单步执行其包含的线程，以及 （可选） 到继续单步执行通过该线程中调用的函数。</span><span class="sxs-lookup"><span data-stu-id="ffa86-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="ffa86-119">StepOut 方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="ffa86-120">这将导致`ICorDebugStepper`到单步执行其包含线程和完成在当前帧将控制权返回给调用的帧。</span><span class="sxs-lookup"><span data-stu-id="ffa86-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="ffa86-121">StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="ffa86-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="ffa86-122">这将导致`ICorDebugStepper`到单步执行其包含的线程，并返回时达到超出指定范围的最后一个代码。</span><span class="sxs-lookup"><span data-stu-id="ffa86-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffa86-123">备注</span><span class="sxs-lookup"><span data-stu-id="ffa86-123">Remarks</span></span>  
 <span data-ttu-id="ffa86-124">`ICorDebugStepper`接口具有以下用途：</span><span class="sxs-lookup"><span data-stu-id="ffa86-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="ffa86-125">它充当步骤命令颁发和完成该命令之间的标识符。</span><span class="sxs-lookup"><span data-stu-id="ffa86-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="ffa86-126">它提供了中央的接口来封装所有单步执行可执行。</span><span class="sxs-lookup"><span data-stu-id="ffa86-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="ffa86-127">它使您能够过早地取消单步执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ffa86-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="ffa86-128">可以有多个分档器每个线程。</span><span class="sxs-lookup"><span data-stu-id="ffa86-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="ffa86-129">例如，逐过程执行函数时可能会命中断点，用户可能想要启动新的单步执行操作，在该函数。</span><span class="sxs-lookup"><span data-stu-id="ffa86-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="ffa86-130">负责调试器来确定如何处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="ffa86-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="ffa86-131">调试器可能想要取消原始单步执行的操作或嵌套的两个操作。</span><span class="sxs-lookup"><span data-stu-id="ffa86-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="ffa86-132">`ICorDebugStepper`接口支持这两种选择。</span><span class="sxs-lookup"><span data-stu-id="ffa86-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="ffa86-133">如果公共语言运行时 (CLR) 进行跨线程的封送调用，分档器可能迁移线程之间。</span><span class="sxs-lookup"><span data-stu-id="ffa86-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffa86-134">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ffa86-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffa86-135">要求</span><span class="sxs-lookup"><span data-stu-id="ffa86-135">Requirements</span></span>  
 <span data-ttu-id="ffa86-136">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffa86-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffa86-137">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffa86-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffa86-138">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffa86-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffa86-139">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffa86-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa86-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffa86-140">See Also</span></span>  
 [<span data-ttu-id="ffa86-141">调试接口</span><span class="sxs-lookup"><span data-stu-id="ffa86-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
