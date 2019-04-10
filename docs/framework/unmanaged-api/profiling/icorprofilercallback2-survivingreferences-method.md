---
title: ICorProfilerCallback2::SurvivingReferences 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.SurvivingReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::SurvivingReferences
helpviewer_keywords:
- ICorProfilerCallback2::SurvivingReferences method [.NET Framework profiling]
- SurvivingReferences method [.NET Framework profiling]
ms.assetid: f165200e-3a91-47f7-88fc-13ff10c8babc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da06ce49415317393b3489c2b8f97afc58f7c83b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191297"
---
# <a name="icorprofilercallback2survivingreferences-method"></a><span data-ttu-id="0ca5c-102">ICorProfilerCallback2::SurvivingReferences 方法</span><span class="sxs-lookup"><span data-stu-id="0ca5c-102">ICorProfilerCallback2::SurvivingReferences Method</span></span>
<span data-ttu-id="0ca5c-103">将堆中对象的布局报告为非压缩垃圾回收的结果。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca5c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ca5c-104">Syntax</span></span>  
  
```  
HRESULT SurvivingReferences(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] ULONG  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ca5c-105">参数</span><span class="sxs-lookup"><span data-stu-id="0ca5c-105">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="0ca5c-106">[in] 作为非压缩垃圾回收的结果而仍存在的连续对象块的数量。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-106">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="0ca5c-107">即，`cSurvivingObjectIDRanges` 的值是 `objectIDRangeStart` 和 `cObjectIDRangeLength` 数组的大小，分别存储每个对象块的 `ObjectID` 和长度。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-107">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="0ca5c-108">`SurvivingReferences` 接来下的两个参数为并行数组。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-108">The next two arguments of `SurvivingReferences` are parallel arrays.</span></span> <span data-ttu-id="0ca5c-109">即，`objectIDRangeStart` 和 `cObjectIDRangeLength` 涉及同一连续对象块。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-109">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="0ca5c-110">[in] `ObjectID` 值的数组，其中每个值均为内存中连续活动对象块的起始地址。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-110">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="0ca5c-111">[in] 整数数组，其中每个整数均为内存中保留下来的连续对象块的大小。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-111">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="0ca5c-112">`objectIDRangeStart` 数组中引用的每个块均指定了大小。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-112">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ca5c-113">备注</span><span class="sxs-lookup"><span data-stu-id="0ca5c-113">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0ca5c-114">此方法将 64 位平台上大于 4 GB 的对象的大小报告为 `MAX_ULONG`。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-114">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="0ca5c-115">对于大于 4 GB 的对象，使用[ICorProfilerCallback4::SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-115">For objects that are larger than 4 GB, use the [ICorProfilerCallback4::SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="0ca5c-116">应按以下方式解释 `objectIDRangeStart` 和 `cObjectIDRangeLength` 数组的元素，以确定垃圾回收后对象是否仍存在。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="0ca5c-117">假定 `ObjectID` 值 (`ObjectID`) 在以下范围内：</span><span class="sxs-lookup"><span data-stu-id="0ca5c-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="0ca5c-118">对于以下范围内 `i` 的任何值，此对象在垃圾回收后仍存在：</span><span class="sxs-lookup"><span data-stu-id="0ca5c-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="0ca5c-119">0 <= `i` < </span><span class="sxs-lookup"><span data-stu-id="0ca5c-119">0 <= `i` < </span></span>`cSurvivingObjectIDRanges`  
  
 <span data-ttu-id="0ca5c-120">非压缩垃圾回收将回收“死”对象占用的内存，但不会压缩释放的空间。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="0ca5c-121">由此，内存返回到堆中，但“活”对象不会移动。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="0ca5c-122">公共语言运行时 (CLR) 调用 `SurvivingReferences` 进行非压缩垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-122">The common language runtime (CLR) calls `SurvivingReferences` for non-compacting garbage collections.</span></span> <span data-ttu-id="0ca5c-123">对于压缩垃圾回收， [icorprofilercallback:: Movedreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)改为调用。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-123">For compacting garbage collections, [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) is called instead.</span></span> <span data-ttu-id="0ca5c-124">单个垃圾回收可针对一个生成进行压缩，而针对另一个生成不进行压缩。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="0ca5c-125">对于任何特定代的垃圾回收，探查器均会收到 `SurvivingReferences` 回调或 `MovedReferences` 回调，但不会同时收到二者。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences` callback or a `MovedReferences` callback, but not both.</span></span>  
  
 <span data-ttu-id="0ca5c-126">由于内部缓冲有限、服务器垃圾回收期间的多个线程报告以及其他原因，在特定的垃圾回收过程中，可能收到多个 `SurvivingReferences` 回调。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-126">Multiple `SurvivingReferences` callbacks might be received during a particular garbage collection, due to limited internal buffering, multiple threads reporting in the case of server garbage collection, and other reasons.</span></span> <span data-ttu-id="0ca5c-127">如果在垃圾回收期间收到多个回调，则信息是累积的 — 任何 `SurvivingReferences` 回调中报告的任何引用都将在垃圾回收后仍然存在。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-127">In the case of multiple callbacks during a garbage collection, the information is cumulative — all references that are reported in any `SurvivingReferences` callback survive the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ca5c-128">要求</span><span class="sxs-lookup"><span data-stu-id="0ca5c-128">Requirements</span></span>  
 <span data-ttu-id="0ca5c-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ca5c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ca5c-130">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ca5c-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ca5c-131">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ca5c-131">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0ca5c-132">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0ca5c-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ca5c-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ca5c-133">See also</span></span>

- [<span data-ttu-id="0ca5c-134">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="0ca5c-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0ca5c-135">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="0ca5c-135">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="0ca5c-136">SurvivingReferences2 方法</span><span class="sxs-lookup"><span data-stu-id="0ca5c-136">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)
