---
title: 分析全局静态函数
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: d1d9b0a4c61ce7c3f8f9792046fb4bddf0fdfa05
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447430"
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="8a4e4-102">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-102">Profiling Global Static Functions</span></span>
<span data-ttu-id="8a4e4-103">本部分介绍分析 API 使用的非托管 API 函数。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-103">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a4e4-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="8a4e4-104">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="8a4e4-105">.NET Framework 版本1分析函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-105">.NET Framework version 1 Profiling Functions</span></span>  
 [<span data-ttu-id="8a4e4-106">FunctionEnter 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-106">FunctionEnter Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 <span data-ttu-id="8a4e4-107">通知探查器控制正在传递到函数。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-107">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="8a4e4-108">.NET Framework 2.0 中弃用。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-108">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="8a4e4-109">FunctionLeave 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-109">FunctionLeave Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 <span data-ttu-id="8a4e4-110">通知探查器某个函数将要返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-110">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="8a4e4-111">.NET Framework 2.0 中弃用。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-111">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="8a4e4-112">FunctionTailcall 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-112">FunctionTailcall Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 <span data-ttu-id="8a4e4-113">通知探查器，当前正在执行的函数即将对另一个函数执行尾调用。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-113">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="8a4e4-114">.NET Framework 2.0 中弃用。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-114">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="8a4e4-115">.NET Framework 版本2分析函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-115">.NET Framework version 2 Profiling Functions</span></span>  
 [<span data-ttu-id="8a4e4-116">FunctionIDMapper 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-116">FunctionIDMapper Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 <span data-ttu-id="8a4e4-117">通知探查器可能会将函数的给定标识符重新映射到备用 ID，以在该函数的[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)和[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)回调中使用。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-117">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="8a4e4-118">还允许探查器指示是否要为该函数接收回调</span><span class="sxs-lookup"><span data-stu-id="8a4e4-118">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="8a4e4-119">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-119">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 <span data-ttu-id="8a4e4-120">通知探查器控制正在传递到函数，并提供有关堆栈帧和函数参数的信息。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-120">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="8a4e4-121">在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-121">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="8a4e4-122">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-122">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 <span data-ttu-id="8a4e4-123">通知探查器函数将要返回到调用方，并提供有关堆栈帧和函数返回值的信息。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-123">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="8a4e4-124">在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-124">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="8a4e4-125">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-125">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 <span data-ttu-id="8a4e4-126">通知探查器，当前正在执行的函数即将对另一个函数执行尾调用，并提供有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-126">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="8a4e4-127">在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-127">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="8a4e4-128">StackSnapshotCallback 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-128">StackSnapshotCallback Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 <span data-ttu-id="8a4e4-129">在堆栈遍历期间，为探查器提供有关每个托管帧和每个托管帧的每个运行的信息，由[ICorProfilerInfo2：:D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法启动。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-129">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="8a4e4-130">.NET Framework 版本4分析函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-130">.NET Framework version 4 Profiling Functions</span></span>  
 [<span data-ttu-id="8a4e4-131">FunctionIDMapper2 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-131">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 <span data-ttu-id="8a4e4-132">通知探查器可能会将函数的给定标识符重新映射到备用 ID，该 ID 将在[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)、 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)和[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)中使用，或者为该函数的[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)和[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-132">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="8a4e4-133">还允许探查器指示是否要接收该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-133">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="8a4e4-134">`FunctionIDMapper2` 使用 `clientData` 参数扩展[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)函数，探查器可能会使用该参数来消除运行时之间的歧义。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-134">`FunctionIDMapper2` extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="8a4e4-135">FunctionEnter3 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-135">FunctionEnter3 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 <span data-ttu-id="8a4e4-136">通知探查器控制正在传递到函数。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-136">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="8a4e4-137">FunctionEnter3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-137">FunctionEnter3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 <span data-ttu-id="8a4e4-138">通知探查器控制正在传递到函数，并提供一个可传递给[ICorProfilerInfo3：： GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)以检索堆栈帧和函数参数的句柄。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-138">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="8a4e4-139">FunctionLeave3 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-139">FunctionLeave3 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 <span data-ttu-id="8a4e4-140">通知探查器控制正在从函数返回。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-140">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="8a4e4-141">FunctionLeave3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-141">FunctionLeave3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 <span data-ttu-id="8a4e4-142">通知探查器正在从某个函数返回控件，并提供一个可传递给[ICorProfilerInfo3：： GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)以检索堆栈帧和返回值的句柄。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-142">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="8a4e4-143">FunctionTailcall3 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-143">FunctionTailcall3 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 <span data-ttu-id="8a4e4-144">通知探查器，当前正在执行的函数即将对另一个函数执行尾调用。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-144">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="8a4e4-145">FunctionTailcall3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="8a4e4-145">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 <span data-ttu-id="8a4e4-146">通知探查器，当前正在执行的函数即将对另一个函数执行尾调用，并提供一个可传递给[ICorProfilerInfo3：： GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)以检索堆栈帧的句柄。</span><span class="sxs-lookup"><span data-stu-id="8a4e4-146">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8a4e4-147">相关章节</span><span class="sxs-lookup"><span data-stu-id="8a4e4-147">Related Sections</span></span>  
 [<span data-ttu-id="8a4e4-148">分析概述</span><span class="sxs-lookup"><span data-stu-id="8a4e4-148">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="8a4e4-149">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="8a4e4-149">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="8a4e4-150">分析枚举</span><span class="sxs-lookup"><span data-stu-id="8a4e4-150">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="8a4e4-151">分析结构</span><span class="sxs-lookup"><span data-stu-id="8a4e4-151">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
