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
ms.openlocfilehash: fdfd3715220785a1fa5285b19e677bf0dc190719
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433078"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="595e9-102">ICorProfilerInfo2::GetObjectGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="595e9-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="595e9-103">获取包含指定对象的堆段。</span><span class="sxs-lookup"><span data-stu-id="595e9-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="595e9-104">语法</span><span class="sxs-lookup"><span data-stu-id="595e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="595e9-105">参数</span><span class="sxs-lookup"><span data-stu-id="595e9-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="595e9-106">中对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="595e9-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="595e9-107">弄指向[COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)结构的指针，该结构描述要进行垃圾回收的代中的内存范围（即块）。</span><span class="sxs-lookup"><span data-stu-id="595e9-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="595e9-108">此范围包含指定的对象。</span><span class="sxs-lookup"><span data-stu-id="595e9-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="595e9-109">备注</span><span class="sxs-lookup"><span data-stu-id="595e9-109">Remarks</span></span>  
 <span data-ttu-id="595e9-110">可从任何探查器回调调用 `GetObjectGeneration` 方法，前提是垃圾回收未进行。</span><span class="sxs-lookup"><span data-stu-id="595e9-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="595e9-111">也就是说，它可从任何回调调用， [ICorProfilerCallback2：： GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)和[ICorProfilerCallback2：： GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)之间发生的回调除外。</span><span class="sxs-lookup"><span data-stu-id="595e9-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="595e9-112">要求</span><span class="sxs-lookup"><span data-stu-id="595e9-112">Requirements</span></span>  
 <span data-ttu-id="595e9-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="595e9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="595e9-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="595e9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="595e9-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="595e9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="595e9-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="595e9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595e9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="595e9-117">See also</span></span>

- [<span data-ttu-id="595e9-118">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="595e9-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="595e9-119">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="595e9-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
