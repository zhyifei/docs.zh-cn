---
title: ICorProfilerCallback::JITCompilationStarted 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b75eebd8d9bf439a0317521a61c06ece3745be0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075316"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="70d7b-102">ICorProfilerCallback::JITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="70d7b-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="70d7b-103">通知探查器在实时 (JIT) 编译器已开始编译函数。</span><span class="sxs-lookup"><span data-stu-id="70d7b-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d7b-104">语法</span><span class="sxs-lookup"><span data-stu-id="70d7b-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70d7b-105">参数</span><span class="sxs-lookup"><span data-stu-id="70d7b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="70d7b-106">[in]从开始编译函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="70d7b-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="70d7b-107">[in]一个值，该值向探查器是否阻止会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="70d7b-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="70d7b-108">值是`true`如果阻塞可能会导致运行时等待调用的线程返回从此回调; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="70d7b-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="70d7b-109">尽管值`true`不会造成损害运行时、 但可能会扭曲分析结果。</span><span class="sxs-lookup"><span data-stu-id="70d7b-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70d7b-110">备注</span><span class="sxs-lookup"><span data-stu-id="70d7b-110">Remarks</span></span>  
 <span data-ttu-id="70d7b-111">可以接收多个对`JITCompilationStarted`并[icorprofilercallback:: Jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)调用每个函数的方式运行时句柄类构造函数。</span><span class="sxs-lookup"><span data-stu-id="70d7b-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="70d7b-112">例如，运行时开始对方法进行 JIT 编译的但类 B 的类构造函数需要运行。</span><span class="sxs-lookup"><span data-stu-id="70d7b-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="70d7b-113">因此，运行时执行 JIT 编译类 B 的构造函数，并运行它。</span><span class="sxs-lookup"><span data-stu-id="70d7b-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="70d7b-114">构造函数正在运行，但可以对一个，这会导致方法 A 再次进行 JIT 编译方法的调用。</span><span class="sxs-lookup"><span data-stu-id="70d7b-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="70d7b-115">在此方案中，将停止方法 A 首次 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="70d7b-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="70d7b-116">但是，这两种方法进行 JIT 编译一个尝试与 JIT 编译事件报告。</span><span class="sxs-lookup"><span data-stu-id="70d7b-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="70d7b-117">如果探查器会通过调用替换为方法的 Microsoft 中间语言 (MSIL) 代码[icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)方法，它必须同时执行此操作`JITCompilationStarted`事件，但它可能会使用相同的 MSIL 块对于两者。</span><span class="sxs-lookup"><span data-stu-id="70d7b-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="70d7b-118">在两个线程同时执行回调的情况下，探查器必须支持 JIT 回调的序列。</span><span class="sxs-lookup"><span data-stu-id="70d7b-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="70d7b-119">例如，调用线程 A `JITCompilationStarted`。</span><span class="sxs-lookup"><span data-stu-id="70d7b-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="70d7b-120">但是，在线程 A 调用前`JITCompilationFinished`，线程 B 调用[icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)从线程 A 的函数 id`JITCompilationStarted`回调。</span><span class="sxs-lookup"><span data-stu-id="70d7b-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="70d7b-121">它可能显示的函数 ID 尚未有效期不应因为调用`JITCompilationFinished`有尚未收到事件探查器。</span><span class="sxs-lookup"><span data-stu-id="70d7b-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="70d7b-122">但是，在这种情况下，函数 ID 有效。</span><span class="sxs-lookup"><span data-stu-id="70d7b-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70d7b-123">要求</span><span class="sxs-lookup"><span data-stu-id="70d7b-123">Requirements</span></span>  
 <span data-ttu-id="70d7b-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70d7b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70d7b-125">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70d7b-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70d7b-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70d7b-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="70d7b-127">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="70d7b-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="70d7b-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="70d7b-128">See also</span></span>

- [<span data-ttu-id="70d7b-129">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="70d7b-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="70d7b-130">JITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="70d7b-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
