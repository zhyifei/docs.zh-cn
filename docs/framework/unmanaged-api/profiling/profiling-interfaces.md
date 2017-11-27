---
title: "分析接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
caps.latest.revision: "31"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5c0423f9c8b01c1289e1107c0c16c59968a6e2a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-interfaces"></a><span data-ttu-id="43838-102">分析接口</span><span class="sxs-lookup"><span data-stu-id="43838-102">Profiling Interfaces</span></span>
<span data-ttu-id="43838-103">本节描述允许对公共语言运行时 (CLR) 正在执行的程序进行分析的非托管接口。</span><span class="sxs-lookup"><span data-stu-id="43838-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43838-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="43838-104">In This Section</span></span>  
 [<span data-ttu-id="43838-105">ICLRProfiling 接口</span><span class="sxs-lookup"><span data-stu-id="43838-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="43838-106">提供[AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)方法，使探查器附加到正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="43838-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="43838-107">Icorprofilerassemblyreferenceprovider 方法</span><span class="sxs-lookup"><span data-stu-id="43838-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="43838-108">探查器能够通知探查器将在中添加的程序集引用的 CLR [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="43838-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="43838-109">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="43838-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="43838-110">提供 CLR 在代码探查器订阅的事件发生时用来通知该探查器的方法。</span><span class="sxs-lookup"><span data-stu-id="43838-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="43838-111">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="43838-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="43838-112">使用 NET Framework 2.0 及更高版本支持的回调扩展 `ICorProfilerCallback` 接口。</span><span class="sxs-lookup"><span data-stu-id="43838-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="43838-113">ICorProfilerCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="43838-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="43838-114">提供 CLR 用于将附加和分离状态信息传递给探查器的回调方法。</span><span class="sxs-lookup"><span data-stu-id="43838-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="43838-115">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="43838-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="43838-116">提供 CLR 用于将信息传递给探查器的回调方法。</span><span class="sxs-lookup"><span data-stu-id="43838-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="43838-117">ICorProfilerCallback5 接口</span><span class="sxs-lookup"><span data-stu-id="43838-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="43838-118">提供用于标识由垃圾回收根引用的对象的传递闭包的方法。</span><span class="sxs-lookup"><span data-stu-id="43838-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="43838-119">ICorProfilerCallback6 接口</span><span class="sxs-lookup"><span data-stu-id="43838-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="43838-120">提供 CLR 用于通知探查器正在加载程序集的回调方法。</span><span class="sxs-lookup"><span data-stu-id="43838-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="43838-121">ICorProfilerCallback7 接口</span><span class="sxs-lookup"><span data-stu-id="43838-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="43838-122">提供公共语言运行时用于通知探查器已更新与内存中模块关联的符号流的回调方法。</span><span class="sxs-lookup"><span data-stu-id="43838-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
 [<span data-ttu-id="43838-123">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="43838-123">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="43838-124">提供允许代码探查器与 CLR 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。</span><span class="sxs-lookup"><span data-stu-id="43838-124">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="43838-125">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="43838-125">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="43838-126">提供按顺序循环访问 CLR 中函数集合的方法。</span><span class="sxs-lookup"><span data-stu-id="43838-126">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="43838-127">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="43838-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="43838-128">提供代码探查器用于与 CLR 通信以控制事件监视及请求信息的方法。</span><span class="sxs-lookup"><span data-stu-id="43838-128">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="43838-129">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="43838-129">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="43838-130">使用 NET Framework 2.0 及更高版本支持的方法扩展 `ICorProfilerInfo` 接口。</span><span class="sxs-lookup"><span data-stu-id="43838-130">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="43838-131">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="43838-131">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="43838-132">使用 `ICorProfilerInfo2` 及更高版本支持的方法扩展 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 接口。</span><span class="sxs-lookup"><span data-stu-id="43838-132">Extends the `ICorProfilerInfo2` interface with methods supported in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] and later versions.</span></span>  
  
 [<span data-ttu-id="43838-133">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="43838-133">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="43838-134">提供一些方法，代码探查器可以使用这些方法与 CLR 通信，从而控制事件监视并请求信息。</span><span class="sxs-lookup"><span data-stu-id="43838-134">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="43838-135">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="43838-135">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="43838-136">提供代码探查器用于与 CLR 通信以控制事件监视的方法。</span><span class="sxs-lookup"><span data-stu-id="43838-136">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="43838-137">ICorProfilerInfo6 接口</span><span class="sxs-lookup"><span data-stu-id="43838-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="43838-138">提供对属于给定 NGen 模块以及在给定方法的正文中内联的所有方法的枚举器。</span><span class="sxs-lookup"><span data-stu-id="43838-138">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="43838-139">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="43838-139">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="43838-140">提供方法以应用新模块定义元数据和使您可以访问的内存中的符号流。</span><span class="sxs-lookup"><span data-stu-id="43838-140">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="43838-141">ICorProfilerModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="43838-141">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="43838-142">提供用于按顺序循环访问应用程序或探查器加载的模块集合的方法。</span><span class="sxs-lookup"><span data-stu-id="43838-142">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="43838-143">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="43838-143">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="43838-144">提供按顺序循环访问集合的冻结对象生成的方法[Ngen.exe （本机映像生成器）](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)。</span><span class="sxs-lookup"><span data-stu-id="43838-144">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="43838-145">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="43838-145">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="43838-146">提供按顺序循环访问 CLR 中线程集合的方法。</span><span class="sxs-lookup"><span data-stu-id="43838-146">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="43838-147">IMethodMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="43838-147">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="43838-148">提供[Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)方法来为新的 Microsoft 中间语言 (MSIL) 函数主体分配内存。</span><span class="sxs-lookup"><span data-stu-id="43838-148">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="43838-149">相关章节</span><span class="sxs-lookup"><span data-stu-id="43838-149">Related Sections</span></span>  
 [<span data-ttu-id="43838-150">分析概述</span><span class="sxs-lookup"><span data-stu-id="43838-150">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="43838-151">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="43838-151">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="43838-152">分析枚举</span><span class="sxs-lookup"><span data-stu-id="43838-152">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="43838-153">分析结构</span><span class="sxs-lookup"><span data-stu-id="43838-153">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
