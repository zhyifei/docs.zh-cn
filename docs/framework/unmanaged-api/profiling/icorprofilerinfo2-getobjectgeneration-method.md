---
title: ICorProfilerInfo2::GetObjectGeneration 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64e362be57a96bbe0f61b964ab413234f30d0ed1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782527"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="401a2-102">ICorProfilerInfo2::GetObjectGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="401a2-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="401a2-103">获取包含指定的对象在堆的段。</span><span class="sxs-lookup"><span data-stu-id="401a2-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="401a2-104">Syntax</span></span>  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="401a2-105">参数</span><span class="sxs-lookup"><span data-stu-id="401a2-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="401a2-106">[in]对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="401a2-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="401a2-107">[out]一个指向[COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)结构，它正进行垃圾回收的代中描述的内存范围 （即块）。</span><span class="sxs-lookup"><span data-stu-id="401a2-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="401a2-108">此范围内包含指定的对象。</span><span class="sxs-lookup"><span data-stu-id="401a2-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="401a2-109">备注</span><span class="sxs-lookup"><span data-stu-id="401a2-109">Remarks</span></span>  
 <span data-ttu-id="401a2-110">`GetObjectGeneration`可能会从任何探查器回调，调用方法，前提是垃圾回收不是正在进行中。</span><span class="sxs-lookup"><span data-stu-id="401a2-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="401a2-111">也就是说，它可以调用从除之间发生的任何回调[ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)并[ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)。</span><span class="sxs-lookup"><span data-stu-id="401a2-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="401a2-112">要求</span><span class="sxs-lookup"><span data-stu-id="401a2-112">Requirements</span></span>  
 <span data-ttu-id="401a2-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="401a2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="401a2-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="401a2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="401a2-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="401a2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="401a2-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="401a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401a2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="401a2-117">See also</span></span>

- [<span data-ttu-id="401a2-118">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="401a2-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="401a2-119">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="401a2-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
