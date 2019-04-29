---
title: 分析接口
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 059fadc5607e76b871083682136fda542ae9bacf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758192"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="ba8ea-102">分析接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-102">Profiling Interfaces</span></span>
<span data-ttu-id="ba8ea-103">本节描述允许对公共语言运行时 (CLR) 正在执行的程序进行分析的非托管接口。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba8ea-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="ba8ea-104">In This Section</span></span>  
 [<span data-ttu-id="ba8ea-105">ICLRProfiling 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="ba8ea-106">提供了[AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)方法，可将探查器附加到正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="ba8ea-107">ICorProfilerAssemblyReferenceProvider 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="ba8ea-108">启用探查器以通知探查器将在中添加的程序集引用的 CLR [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="ba8ea-109">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="ba8ea-110">提供 CLR 在代码探查器订阅的事件发生时用来通知该探查器的方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="ba8ea-111">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="ba8ea-112">使用 NET Framework 2.0 及更高版本支持的回调扩展 `ICorProfilerCallback` 接口。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="ba8ea-113">ICorProfilerCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="ba8ea-114">提供 CLR 用于将附加和分离状态信息传递给探查器的回调方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="ba8ea-115">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="ba8ea-116">提供 CLR 用于将信息传递给探查器的回调方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="ba8ea-117">ICorProfilerCallback5 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="ba8ea-118">提供用于标识由垃圾回收根引用的对象的传递闭包的方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="ba8ea-119">ICorProfilerCallback6 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="ba8ea-120">提供 CLR 用于通知探查器正在加载程序集的回调方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="ba8ea-121">ICorProfilerCallback7 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="ba8ea-122">提供公共语言运行时用于通知探查器已更新与内存中模块关联的符号流的回调方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="ba8ea-123">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-123">ICorProfilerCallback8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
<span data-ttu-id="ba8ea-124">提供了公共语言运行时用于通知探查器中的动态方法的 JIT 编译已启动和完成的回调方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="ba8ea-125">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-125">ICorProfilerCallback9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
<span data-ttu-id="ba8ea-126">提供公共语言运行时用于通知探查器垃圾回收并随后卸载的动态方法的回调方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="ba8ea-127">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-127">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="ba8ea-128">提供允许代码探查器与 CLR 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="ba8ea-129">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-129">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="ba8ea-130">提供按顺序循环访问 CLR 中函数集合的方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="ba8ea-131">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-131">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="ba8ea-132">提供代码探查器用于与 CLR 通信以控制事件监视及请求信息的方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="ba8ea-133">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-133">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="ba8ea-134">使用 NET Framework 2.0 及更高版本支持的方法扩展 `ICorProfilerInfo` 接口。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="ba8ea-135">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-135">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="ba8ea-136">使用 `ICorProfilerInfo2` 及更高版本支持的方法扩展 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 接口。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-136">Extends the `ICorProfilerInfo2` interface with methods supported in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] and later versions.</span></span>  
  
 [<span data-ttu-id="ba8ea-137">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-137">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="ba8ea-138">提供一些方法，代码探查器可以使用这些方法与 CLR 通信，从而控制事件监视并请求信息。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="ba8ea-139">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-139">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="ba8ea-140">提供代码探查器用于与 CLR 通信以控制事件监视的方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="ba8ea-141">ICorProfilerInfo6 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-141">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="ba8ea-142">提供对属于给定的 NGen 模块且是内联给定方法的正文中的所有方法的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="ba8ea-143">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-143">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="ba8ea-144">提供用于将新应用的方法对模块定义元数据中，并提供对内存中的符号流的访问。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="ba8ea-145">ICorProfilerModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-145">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="ba8ea-146">提供用于按顺序循环访问应用程序或探查器加载的模块集合的方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="ba8ea-147">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-147">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="ba8ea-148">提供了按顺序循环访问由生成的冻结对象的集合的方法[Ngen.exe （本机映像生成器）](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="ba8ea-149">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-149">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="ba8ea-150">提供按顺序循环访问 CLR 中线程集合的方法。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="ba8ea-151">IMethodMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="ba8ea-151">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="ba8ea-152">提供了[Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)方法，以用于新的 Microsoft 中间语言 (MSIL) 函数主体分配内存。</span><span class="sxs-lookup"><span data-stu-id="ba8ea-152">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ba8ea-153">相关章节</span><span class="sxs-lookup"><span data-stu-id="ba8ea-153">Related Sections</span></span>  
 [<span data-ttu-id="ba8ea-154">分析概述</span><span class="sxs-lookup"><span data-stu-id="ba8ea-154">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="ba8ea-155">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="ba8ea-155">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="ba8ea-156">分析枚举</span><span class="sxs-lookup"><span data-stu-id="ba8ea-156">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="ba8ea-157">分析结构</span><span class="sxs-lookup"><span data-stu-id="ba8ea-157">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
