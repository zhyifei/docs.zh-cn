---
title: ICorProfilerCallback2::GarbageCollectionStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
ms.openlocfilehash: ed2553f2d971deefd85f731dd39f383cd096c5b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439811"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="f8698-102">ICorProfilerCallback2::GarbageCollectionStarted 方法</span><span class="sxs-lookup"><span data-stu-id="f8698-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="f8698-103">通知代码探查器垃圾回收已启动。</span><span class="sxs-lookup"><span data-stu-id="f8698-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8698-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8698-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8698-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8698-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="f8698-106">中`generationCollected` 数组中的总项数。</span><span class="sxs-lookup"><span data-stu-id="f8698-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="f8698-107">中布尔值的数组，如果此垃圾回收正在收集与数组索引对应的代，则 `true` 此数组;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="f8698-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="f8698-108">数组由[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)枚举的一个值进行索引，该枚举指示代。</span><span class="sxs-lookup"><span data-stu-id="f8698-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="f8698-109">中一个[COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)枚举的值，该值指示导致垃圾回收的原因。</span><span class="sxs-lookup"><span data-stu-id="f8698-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8698-110">备注</span><span class="sxs-lookup"><span data-stu-id="f8698-110">Remarks</span></span>  
 <span data-ttu-id="f8698-111">与此垃圾回收相关的所有回调都将在 `GarbageCollectionStarted` 回调和相应的[ICorProfilerCallback2：： GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)回调之间发生。</span><span class="sxs-lookup"><span data-stu-id="f8698-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="f8698-112">这些回调不需要在同一线程上发生。</span><span class="sxs-lookup"><span data-stu-id="f8698-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="f8698-113">探查器在 `GarbageCollectionStarted` 回调过程中检查其原始位置中的对象是安全的。</span><span class="sxs-lookup"><span data-stu-id="f8698-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="f8698-114">垃圾回收器将在从 `GarbageCollectionStarted`返回后开始移动对象。</span><span class="sxs-lookup"><span data-stu-id="f8698-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="f8698-115">在探查器从此回调返回后，探查器应在收到 `ICorProfilerCallback2::GarbageCollectionFinished` 回调之前，将所有对象 Id 视为无效。</span><span class="sxs-lookup"><span data-stu-id="f8698-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8698-116">要求</span><span class="sxs-lookup"><span data-stu-id="f8698-116">Requirements</span></span>  
 <span data-ttu-id="f8698-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8698-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8698-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8698-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8698-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8698-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8698-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8698-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8698-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8698-121">See also</span></span>

- [<span data-ttu-id="f8698-122">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f8698-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f8698-123">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="f8698-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
