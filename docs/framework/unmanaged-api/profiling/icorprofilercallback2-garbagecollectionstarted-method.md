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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5f9104dded44540c47c955c15354d8d76a27650
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183061"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="0f676-102">ICorProfilerCallback2::GarbageCollectionStarted 方法</span><span class="sxs-lookup"><span data-stu-id="0f676-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="0f676-103">通知垃圾回收已启动代码探查器。</span><span class="sxs-lookup"><span data-stu-id="0f676-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f676-104">语法</span><span class="sxs-lookup"><span data-stu-id="0f676-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f676-105">参数</span><span class="sxs-lookup"><span data-stu-id="0f676-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="0f676-106">[in]中的条目总数`generationCollected`数组。</span><span class="sxs-lookup"><span data-stu-id="0f676-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="0f676-107">[in]布尔值，即的数组`true`与数组索引相对应的代是否正被收集的此垃圾回收; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="0f676-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="0f676-108">数组进行索引的值[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)枚举，指示生成。</span><span class="sxs-lookup"><span data-stu-id="0f676-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="0f676-109">[in]值为[COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)已引发指示垃圾回收的原因的枚举。</span><span class="sxs-lookup"><span data-stu-id="0f676-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f676-110">备注</span><span class="sxs-lookup"><span data-stu-id="0f676-110">Remarks</span></span>  
 <span data-ttu-id="0f676-111">所有属于此垃圾回收的回调之间将发生`GarbageCollectionStarted`回调和相应[ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="0f676-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="0f676-112">这些回调，无需在同一线程上。</span><span class="sxs-lookup"><span data-stu-id="0f676-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="0f676-113">它是安全的探查器来检查在其原始位置中的对象`GarbageCollectionStarted`回调。</span><span class="sxs-lookup"><span data-stu-id="0f676-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="0f676-114">垃圾回收器将从返回后开始移动对象`GarbageCollectionStarted`。</span><span class="sxs-lookup"><span data-stu-id="0f676-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="0f676-115">探查器从此回调返回后，探查器应考虑所有的对象 Id 为无效，直到收到`ICorProfilerCallback2::GarbageCollectionFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="0f676-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f676-116">要求</span><span class="sxs-lookup"><span data-stu-id="0f676-116">Requirements</span></span>  
 <span data-ttu-id="0f676-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f676-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f676-118">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f676-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f676-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f676-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0f676-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0f676-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0f676-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f676-121">See also</span></span>

- [<span data-ttu-id="0f676-122">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="0f676-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0f676-123">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="0f676-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
