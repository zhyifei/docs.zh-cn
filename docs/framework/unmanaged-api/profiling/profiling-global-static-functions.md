---
title: 分析全局静态函数
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bb5d93c91de857ebbee63009cad73fba7e1d284
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758244"
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="962bb-102">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="962bb-102">Profiling Global Static Functions</span></span>
<span data-ttu-id="962bb-103">本节描述分析 API 使用的非托管的 API 函数。</span><span class="sxs-lookup"><span data-stu-id="962bb-103">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="962bb-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="962bb-104">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="962bb-105">.NET framework 版本 1 分析函数</span><span class="sxs-lookup"><span data-stu-id="962bb-105">.NET Framework version 1 Profiling Functions</span></span>  
 [<span data-ttu-id="962bb-106">FunctionEnter 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-106">FunctionEnter Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 <span data-ttu-id="962bb-107">通知探查器控件传递给函数。</span><span class="sxs-lookup"><span data-stu-id="962bb-107">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="962bb-108">.NET Framework 2.0 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="962bb-108">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="962bb-109">FunctionLeave 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-109">FunctionLeave Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 <span data-ttu-id="962bb-110">通知探查器函数以返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="962bb-110">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="962bb-111">.NET Framework 2.0 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="962bb-111">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="962bb-112">FunctionTailcall 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-112">FunctionTailcall Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 <span data-ttu-id="962bb-113">通知探查器当前正在执行的函数将要执行到另一个函数的结尾调用。</span><span class="sxs-lookup"><span data-stu-id="962bb-113">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="962bb-114">.NET Framework 2.0 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="962bb-114">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="962bb-115">.NET framework 版本 2 分析函数</span><span class="sxs-lookup"><span data-stu-id="962bb-115">.NET Framework version 2 Profiling Functions</span></span>  
 [<span data-ttu-id="962bb-116">FunctionIDMapper 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-116">FunctionIDMapper Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 <span data-ttu-id="962bb-117">通知探查器函数的给定的标识符可能被重新映射到要在中使用的备用 ID [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)， [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)，和[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="962bb-117">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="962bb-118">此外使探查器以指示它是否想要为该函数接收回调</span><span class="sxs-lookup"><span data-stu-id="962bb-118">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="962bb-119">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-119">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 <span data-ttu-id="962bb-120">通知探查器，控制被传递给函数，并介绍有关堆栈帧和函数参数。</span><span class="sxs-lookup"><span data-stu-id="962bb-120">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="962bb-121">中已弃用[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="962bb-121">Deprecated in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="962bb-122">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-122">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 <span data-ttu-id="962bb-123">函数即将返回给调用方，并提供有关堆栈帧和函数返回值的信息，请通知探查器。</span><span class="sxs-lookup"><span data-stu-id="962bb-123">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="962bb-124">中已弃用[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="962bb-124">Deprecated in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="962bb-125">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-125">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 <span data-ttu-id="962bb-126">通知探查器当前正在执行的函数将要执行到另一个函数的结尾调用并提供有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="962bb-126">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="962bb-127">中已弃用[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="962bb-127">Deprecated in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="962bb-128">StackSnapshotCallback 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-128">StackSnapshotCallback Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 <span data-ttu-id="962bb-129">提供有关每个托管的帧和非托管帧的每次运行在堆栈上的堆栈遍历，启动的过程信息，以及探查器[ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="962bb-129">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="962bb-130">.NET framework 版本 4 分析函数</span><span class="sxs-lookup"><span data-stu-id="962bb-130">.NET Framework version 4 Profiling Functions</span></span>  
 [<span data-ttu-id="962bb-131">FunctionIDMapper2 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-131">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 <span data-ttu-id="962bb-132">通知探查器函数的给定的标识符可能被重新映射到要在中使用的备用 ID [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)， [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)，和[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)，或[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，并且[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="962bb-132">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="962bb-133">此外使探查器以指示它是否想要接收该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="962bb-133">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="962bb-134">`FunctionIDMapper2` 扩展了[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)函数与`clientData`探查器可能用于消除运行时间歧义的参数。</span><span class="sxs-lookup"><span data-stu-id="962bb-134">`FunctionIDMapper2` extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="962bb-135">FunctionEnter3 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-135">FunctionEnter3 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 <span data-ttu-id="962bb-136">通知探查器控件传递给函数。</span><span class="sxs-lookup"><span data-stu-id="962bb-136">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="962bb-137">FunctionEnter3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-137">FunctionEnter3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 <span data-ttu-id="962bb-138">通知探查器正在将控件传递给函数，并提供句柄，可传递给[ICorProfilerInfo3::GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)以检索堆栈帧和函数参数。</span><span class="sxs-lookup"><span data-stu-id="962bb-138">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="962bb-139">FunctionLeave3 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-139">FunctionLeave3 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 <span data-ttu-id="962bb-140">通知探查器从函数返回控制。</span><span class="sxs-lookup"><span data-stu-id="962bb-140">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="962bb-141">FunctionLeave3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-141">FunctionLeave3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 <span data-ttu-id="962bb-142">通知探查器一个函数，从正在返回控制和提供句柄，可传递给[ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)检索堆栈帧和返回值。</span><span class="sxs-lookup"><span data-stu-id="962bb-142">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="962bb-143">FunctionTailcall3 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-143">FunctionTailcall3 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 <span data-ttu-id="962bb-144">通知探查器当前正在执行的函数将要执行到另一个函数的结尾调用。</span><span class="sxs-lookup"><span data-stu-id="962bb-144">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="962bb-145">FunctionTailcall3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="962bb-145">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 <span data-ttu-id="962bb-146">通知当前正在执行的函数将执行到另一个函数的结尾调用探查器和提供句柄，可传递给[ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)检索堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="962bb-146">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="962bb-147">相关章节</span><span class="sxs-lookup"><span data-stu-id="962bb-147">Related Sections</span></span>  
 [<span data-ttu-id="962bb-148">分析概述</span><span class="sxs-lookup"><span data-stu-id="962bb-148">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="962bb-149">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="962bb-149">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="962bb-150">分析枚举</span><span class="sxs-lookup"><span data-stu-id="962bb-150">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="962bb-151">分析结构</span><span class="sxs-lookup"><span data-stu-id="962bb-151">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
