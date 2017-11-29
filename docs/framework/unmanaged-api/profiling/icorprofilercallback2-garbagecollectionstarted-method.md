---
title: "ICorProfilerCallback2::GarbageCollectionStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e79eea059fab4810ece12dbc264f3d3b08b7ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="fa9f6-102">ICorProfilerCallback2::GarbageCollectionStarted 方法</span><span class="sxs-lookup"><span data-stu-id="fa9f6-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="fa9f6-103">通知垃圾回收已启动代码探查器。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa9f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa9f6-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa9f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa9f6-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="fa9f6-106">[in]中的总项数`generationCollected`数组。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="fa9f6-107">[in]布尔值，这些值的数组`true`如果对应的数组索引生成正在收集的此垃圾回收; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="fa9f6-108">数组进行索引的值由[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)枚举，该值指示生成。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="fa9f6-109">[in]值为[COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)已引发指示垃圾回收的原因的枚举。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa9f6-110">备注</span><span class="sxs-lookup"><span data-stu-id="fa9f6-110">Remarks</span></span>  
 <span data-ttu-id="fa9f6-111">所有适用于此垃圾回收的回调之间将发生`GarbageCollectionStarted`回调和相应[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="fa9f6-112">这些回调不需要在同一线程上发生。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="fa9f6-113">它是安全的探查器检查在其原始位置中的对象`GarbageCollectionStarted`回调。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="fa9f6-114">垃圾回收器将从返回后开始移动对象`GarbageCollectionStarted`。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="fa9f6-115">探查器从此回调返回后，探查器应考虑为无效，直至其收到的所有对象 Id`ICorProfilerCallback2::GarbageCollectionFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa9f6-116">要求</span><span class="sxs-lookup"><span data-stu-id="fa9f6-116">Requirements</span></span>  
 <span data-ttu-id="fa9f6-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa9f6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa9f6-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa9f6-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa9f6-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa9f6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa9f6-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa9f6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9f6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa9f6-121">See Also</span></span>  
 [<span data-ttu-id="fa9f6-122">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="fa9f6-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="fa9f6-123">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="fa9f6-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
