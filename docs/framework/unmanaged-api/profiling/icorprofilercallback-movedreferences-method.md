---
title: ICorProfilerCallback::MovedReferences 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4611b8c186e0293dae73cee4f9d845bb44c167c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073541"
---
# <a name="icorprofilercallbackmovedreferences-method"></a><span data-ttu-id="06941-102">ICorProfilerCallback::MovedReferences 方法</span><span class="sxs-lookup"><span data-stu-id="06941-102">ICorProfilerCallback::MovedReferences Method</span></span>
<span data-ttu-id="06941-103">调用以报告堆中对象的新布局（压缩垃圾回收产生的结果）。</span><span class="sxs-lookup"><span data-stu-id="06941-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06941-104">语法</span><span class="sxs-lookup"><span data-stu-id="06941-104">Syntax</span></span>  
  
```  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="06941-105">参数</span><span class="sxs-lookup"><span data-stu-id="06941-105">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="06941-106">[in] 因压缩垃圾回收而被移动的连续对象的块数。</span><span class="sxs-lookup"><span data-stu-id="06941-106">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="06941-107">即 `cMovedObjectIDRanges` 的值是 `oldObjectIDRangeStart`、`newObjectIDRangeStart` 和 `cObjectIDRangeLength` 数组的总大小。</span><span class="sxs-lookup"><span data-stu-id="06941-107">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="06941-108">`MovedReferences` 的接下来的三个参数是并行数组。</span><span class="sxs-lookup"><span data-stu-id="06941-108">The next three arguments of `MovedReferences` are parallel arrays.</span></span> <span data-ttu-id="06941-109">换言之，`oldObjectIDRangeStart[i]`、`newObjectIDRangeStart[i]` 和 `cObjectIDRangeLength[i]` 都涉及单个连续对象单块。</span><span class="sxs-lookup"><span data-stu-id="06941-109">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="06941-110">[in] `ObjectID` 值的数组，其中每个值均为内存中连续活动对象块的旧（垃圾回收前）起始地址。</span><span class="sxs-lookup"><span data-stu-id="06941-110">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="06941-111">[in] `ObjectID` 值的数组，其中每个值均为内存中连续活动对象块的新（垃圾回收后）起始地址。</span><span class="sxs-lookup"><span data-stu-id="06941-111">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="06941-112">[in] 整数数组，其中每个整数均为内存中的连续对象块的大小。</span><span class="sxs-lookup"><span data-stu-id="06941-112">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="06941-113">`oldObjectIDRangeStart` 和 `newObjectIDRangeStart` 数组中引用的每个块均有指定的大小。</span><span class="sxs-lookup"><span data-stu-id="06941-113">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06941-114">备注</span><span class="sxs-lookup"><span data-stu-id="06941-114">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="06941-115">此方法将 64 位平台上大于 4 GB 的对象的大小报告为 `MAX_ULONG`。</span><span class="sxs-lookup"><span data-stu-id="06941-115">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="06941-116">若要获取大于 4 GB 的对象的大小，请使用[ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="06941-116">To get the size of objects that are larger than 4 GB, use the [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="06941-117">压缩垃圾回收器将收回由不活动对象占用的内存，但不会压缩释放的空间。</span><span class="sxs-lookup"><span data-stu-id="06941-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="06941-118">因此，可能在堆中移动活动对象，并且由以前的通知分发的 `ObjectID` 值也可能更改。</span><span class="sxs-lookup"><span data-stu-id="06941-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="06941-119">假定现有 `ObjectID` 值 (`oldObjectID`) 在以下范围内：</span><span class="sxs-lookup"><span data-stu-id="06941-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="06941-120">在这种情况下，从范围起始到对象起始位置的偏移量如下所示：</span><span class="sxs-lookup"><span data-stu-id="06941-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="06941-121">对于以下范围内的任何 `i` 值：</span><span class="sxs-lookup"><span data-stu-id="06941-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="06941-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="06941-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="06941-123">可以按以下方式计算出新的 `ObjectID`：</span><span class="sxs-lookup"><span data-stu-id="06941-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="06941-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span><span class="sxs-lookup"><span data-stu-id="06941-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="06941-125">`MovedReferences` 传递的 `ObjectID` 值在回调过程中均是无效的，因为垃圾回收可能正处于将对象从旧位置移到新位置的阶段。</span><span class="sxs-lookup"><span data-stu-id="06941-125">None of the `ObjectID` values passed by `MovedReferences` are valid during the callback itself, because the garbage collection might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="06941-126">因此，探查器不应在 `MovedReferences` 调用期间尝试检查对象。</span><span class="sxs-lookup"><span data-stu-id="06941-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences` call.</span></span> <span data-ttu-id="06941-127">一个[ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)回调指示所有对象都已都移到其新位置并且可以执行检查。</span><span class="sxs-lookup"><span data-stu-id="06941-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06941-128">要求</span><span class="sxs-lookup"><span data-stu-id="06941-128">Requirements</span></span>  
 <span data-ttu-id="06941-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06941-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06941-130">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06941-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06941-131">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06941-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06941-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06941-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06941-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="06941-133">See also</span></span>

- [<span data-ttu-id="06941-134">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="06941-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="06941-135">MovedReferences2 方法</span><span class="sxs-lookup"><span data-stu-id="06941-135">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)
- [<span data-ttu-id="06941-136">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="06941-136">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="06941-137">分析</span><span class="sxs-lookup"><span data-stu-id="06941-137">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
