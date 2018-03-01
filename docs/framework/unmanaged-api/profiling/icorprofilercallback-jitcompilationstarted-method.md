---
title: "ICorProfilerCallback::JITCompilationStarted 方法"
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
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 12a25f452ccb121ef7ebcae05048eb7116b4ac48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="21899-102">ICorProfilerCallback::JITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="21899-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="21899-103">通知探查器已开始在实时 (JIT) 编译器将函数编译。</span><span class="sxs-lookup"><span data-stu-id="21899-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21899-104">语法</span><span class="sxs-lookup"><span data-stu-id="21899-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21899-105">参数</span><span class="sxs-lookup"><span data-stu-id="21899-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="21899-106">[in]正在为其启动编译的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="21899-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="21899-107">[in]一个值，该值向探查器阻止是否会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="21899-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="21899-108">值是`true`如果阻止可能导致运行时，等待调用的线程，以返回从此回调; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="21899-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="21899-109">尽管值`true`不会造成损害运行时、 但可能会扭曲分析结果。</span><span class="sxs-lookup"><span data-stu-id="21899-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21899-110">备注</span><span class="sxs-lookup"><span data-stu-id="21899-110">Remarks</span></span>  
 <span data-ttu-id="21899-111">可以接收多个对`JITCompilationStarted`和[icorprofilercallback:: Jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)调用为每个函数由于的方式运行时句柄类构造函数。</span><span class="sxs-lookup"><span data-stu-id="21899-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="21899-112">例如，运行时开始对方法 A JIT 编译，但类 B 的类构造函数需要运行。</span><span class="sxs-lookup"><span data-stu-id="21899-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="21899-113">因此，运行时 JIT 编译类 B 的构造函数和运行它。</span><span class="sxs-lookup"><span data-stu-id="21899-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="21899-114">在运行时构造函数，它将调用方法 A，从而导致方法 A 再次进行 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="21899-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="21899-115">在此方案中，将停止的方法的第一个的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="21899-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="21899-116">但是，对 JIT 编译方法 A 两次尝试使用 JIT 编译事件报告。</span><span class="sxs-lookup"><span data-stu-id="21899-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="21899-117">如果探查器打算通过调用替换方法的 Microsoft 中间语言 (MSIL) 代码[icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)方法，它必须执行此操作两个`JITCompilationStarted`事件，但它可能使用相同的 MSIL 块有关两者。</span><span class="sxs-lookup"><span data-stu-id="21899-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="21899-118">在两个线程同时执行回调的情况下，探查器必须支持 JIT 回调的序列。</span><span class="sxs-lookup"><span data-stu-id="21899-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="21899-119">例如，调用线程 A `JITCompilationStarted`。</span><span class="sxs-lookup"><span data-stu-id="21899-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="21899-120">但是，在线程的调用之前`JITCompilationFinished`，线程 B 调用[icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)从线程 A 的函数 id`JITCompilationStarted`回调。</span><span class="sxs-lookup"><span data-stu-id="21899-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="21899-121">它可能会出现，函数 ID 尚未有效期不应由于调用`JITCompilationFinished`具有尚未收到探查器。</span><span class="sxs-lookup"><span data-stu-id="21899-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="21899-122">但是，在与此类似情况下，该函数 ID 是有效的。</span><span class="sxs-lookup"><span data-stu-id="21899-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21899-123">惠?</span><span class="sxs-lookup"><span data-stu-id="21899-123">Requirements</span></span>  
 <span data-ttu-id="21899-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21899-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21899-125">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21899-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21899-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21899-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21899-127">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21899-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21899-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="21899-128">See Also</span></span>  
 [<span data-ttu-id="21899-129">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="21899-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="21899-130">JITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="21899-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
