---
title: ICorProfilerInfo2::GetGenerationBounds 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec0f953ecd0b578d25bcbe155f4bec97274e176c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489835"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="6847c-102">ICorProfilerInfo2::GetGenerationBounds 方法</span><span class="sxs-lookup"><span data-stu-id="6847c-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="6847c-103">获取属于堆段的内存区域，堆段构成各代垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="6847c-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6847c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6847c-104">Syntax</span></span>  
  
```  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6847c-105">参数</span><span class="sxs-lookup"><span data-stu-id="6847c-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="6847c-106">[in] 由调用方为 `ranges` 数组分配的元素数目。</span><span class="sxs-lookup"><span data-stu-id="6847c-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="6847c-107">[out] 指向指定范围总数的整数的指针，部分或所有范围都将在 `ranges` 数组中返回。</span><span class="sxs-lookup"><span data-stu-id="6847c-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="6847c-108">[out]一个数组[COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)结构，其中每个正在进行垃圾回收的代中描述的内存范围 （即块）。</span><span class="sxs-lookup"><span data-stu-id="6847c-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6847c-109">备注</span><span class="sxs-lookup"><span data-stu-id="6847c-109">Remarks</span></span>  
 <span data-ttu-id="6847c-110">可以从任何探查器回调调用 `GetGenerationBounds` 方法，前提是当前未进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="6847c-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="6847c-111">也就是说，它可以从除之间发生的任何回调调用[ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)并[ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)。</span><span class="sxs-lookup"><span data-stu-id="6847c-111">That is, it can be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
 <span data-ttu-id="6847c-112">大多数代切换都发生在垃圾回收期间。</span><span class="sxs-lookup"><span data-stu-id="6847c-112">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="6847c-113">在回收之间，代可能会增长，但通常不会反复切换。</span><span class="sxs-lookup"><span data-stu-id="6847c-113">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="6847c-114">因此，调用 `GetGenerationBounds` 最具特色的地方在于 `ICorProfilerCallback2::GarbageCollectionStarted` 和 `ICorProfilerCallback2::GarbageCollectionFinished` 中。</span><span class="sxs-lookup"><span data-stu-id="6847c-114">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="6847c-115">在程序启动期间，某些对象是由公共语言运行时 (CLR) 自身分配的，通常发生在第 3 代和第 0 代中。</span><span class="sxs-lookup"><span data-stu-id="6847c-115">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="6847c-116">因此，当托管代码开始执行时，这些代将已经包含对象。</span><span class="sxs-lookup"><span data-stu-id="6847c-116">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="6847c-117">第 1 代和第 2 代通常将为空，但由垃圾回收器生成的虚拟对象除外。</span><span class="sxs-lookup"><span data-stu-id="6847c-117">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="6847c-118">（虚拟对象的大小在 32 位的 CLR 实现中为 12 个字节；在 64 位实现中更大。）你还可能看到本机映像生成器 (NGen.exe) 生成的模块内的第 2 代范围。</span><span class="sxs-lookup"><span data-stu-id="6847c-118">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="6847c-119">在这种情况下，第 2 代中的对象是*冻结对象*，NGen.exe 运行时而不是由垃圾回收器分配的。</span><span class="sxs-lookup"><span data-stu-id="6847c-119">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="6847c-120">此函数使用调用方分配的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6847c-120">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6847c-121">要求</span><span class="sxs-lookup"><span data-stu-id="6847c-121">Requirements</span></span>  
 <span data-ttu-id="6847c-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6847c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6847c-123">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6847c-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6847c-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6847c-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6847c-125">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6847c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6847c-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6847c-126">See also</span></span>
- [<span data-ttu-id="6847c-127">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="6847c-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="6847c-128">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="6847c-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="6847c-129">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="6847c-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="6847c-130">分析</span><span class="sxs-lookup"><span data-stu-id="6847c-130">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
