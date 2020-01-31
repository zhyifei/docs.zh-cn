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
ms.openlocfilehash: b75de955e3b6857c9cc1b5411df4b0f262c4cb9a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862693"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="2e63b-102">ICorProfilerInfo2::GetObjectGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="2e63b-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="2e63b-103">获取包含指定对象的堆段。</span><span class="sxs-lookup"><span data-stu-id="2e63b-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e63b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e63b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e63b-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e63b-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="2e63b-106">中对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="2e63b-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="2e63b-107">弄指向[COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md)结构的指针，该结构描述要进行垃圾回收的代中的内存范围（即块）。</span><span class="sxs-lookup"><span data-stu-id="2e63b-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="2e63b-108">此范围包含指定的对象。</span><span class="sxs-lookup"><span data-stu-id="2e63b-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e63b-109">备注</span><span class="sxs-lookup"><span data-stu-id="2e63b-109">Remarks</span></span>  
 <span data-ttu-id="2e63b-110">可从任何探查器回调调用 `GetObjectGeneration` 方法，前提是垃圾回收未进行。</span><span class="sxs-lookup"><span data-stu-id="2e63b-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="2e63b-111">也就是说，它可从任何回调调用， [ICorProfilerCallback2：： GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md)和[ICorProfilerCallback2：： GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)之间发生的回调除外。</span><span class="sxs-lookup"><span data-stu-id="2e63b-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e63b-112">需求</span><span class="sxs-lookup"><span data-stu-id="2e63b-112">Requirements</span></span>  
 <span data-ttu-id="2e63b-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e63b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e63b-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e63b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2e63b-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e63b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e63b-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e63b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e63b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e63b-117">See also</span></span>

- [<span data-ttu-id="2e63b-118">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="2e63b-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2e63b-119">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="2e63b-119">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
