---
title: "ICorProfilerInfo2::GetObjectGeneration 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetObjectGeneration
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e90139f96638dbb1a183f98e754838ff52424fc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="3ac68-102">ICorProfilerInfo2::GetObjectGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="3ac68-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="3ac68-103">获取包含指定的对象的堆的段。</span><span class="sxs-lookup"><span data-stu-id="3ac68-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ac68-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ac68-104">Syntax</span></span>  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ac68-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ac68-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="3ac68-106">[in]对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="3ac68-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="3ac68-107">[out]指向的指针[COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)结构，正在进行的垃圾回收的代中描述的内存范围 （即块）。</span><span class="sxs-lookup"><span data-stu-id="3ac68-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="3ac68-108">此范围包含指定的对象。</span><span class="sxs-lookup"><span data-stu-id="3ac68-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ac68-109">备注</span><span class="sxs-lookup"><span data-stu-id="3ac68-109">Remarks</span></span>  
 <span data-ttu-id="3ac68-110">`GetObjectGeneration`可以从任何探查器回调，调用方法，前提是垃圾回收不正在进行。</span><span class="sxs-lookup"><span data-stu-id="3ac68-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="3ac68-111">也就是说，它可以从除外之间发生的任何回调调用[icorprofilercallback2:: Garbagecollectionstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)和[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3ac68-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ac68-112">要求</span><span class="sxs-lookup"><span data-stu-id="3ac68-112">Requirements</span></span>  
 <span data-ttu-id="3ac68-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ac68-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ac68-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ac68-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ac68-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ac68-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ac68-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ac68-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac68-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ac68-117">See Also</span></span>  
 [<span data-ttu-id="3ac68-118">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="3ac68-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="3ac68-119">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="3ac68-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
