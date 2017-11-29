---
title: "COR_PRF_GC_GENERATION_RANGE 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_GENERATION_RANGE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords: COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e2fd546a88f34906ab37e36377f67c26e80b2799
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcgenerationrange-structure"></a><span data-ttu-id="ae4b9-102">COR_PRF_GC_GENERATION_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="ae4b9-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="ae4b9-103">描述一个正进行垃圾回收的内存范围（即块）。</span><span class="sxs-lookup"><span data-stu-id="ae4b9-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae4b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae4b9-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="ae4b9-105">成员</span><span class="sxs-lookup"><span data-stu-id="ae4b9-105">Members</span></span>  
  
|<span data-ttu-id="ae4b9-106">成员</span><span class="sxs-lookup"><span data-stu-id="ae4b9-106">Member</span></span>|<span data-ttu-id="ae4b9-107">描述</span><span class="sxs-lookup"><span data-stu-id="ae4b9-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="ae4b9-108">值为[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)所属指定的内存块的与其生成的枚举。</span><span class="sxs-lookup"><span data-stu-id="ae4b9-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="ae4b9-109">一个指定的内存块的起始位置的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="ae4b9-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="ae4b9-110">指向一个整数，指定的内存块 （即，在块中使用的内存量） 已使用部分大小的指针。</span><span class="sxs-lookup"><span data-stu-id="ae4b9-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="ae4b9-111">指向一个整数，指定内存块 （即块保留的内存量） 的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="ae4b9-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae4b9-112">备注</span><span class="sxs-lookup"><span data-stu-id="ae4b9-112">Remarks</span></span>  
 <span data-ttu-id="ae4b9-113">`rangeLength`值一定要准确才[icorprofilerinfo2:: Getgenerationbounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)或[icorprofilerinfo2:: Getobjectgeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)，这两个使用`COR_PRF_GC_GENERATION_RANGE`结构，请从调用[icorprofilercallback2:: Garbagecollectionstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)或[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ae4b9-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae4b9-114">要求</span><span class="sxs-lookup"><span data-stu-id="ae4b9-114">Requirements</span></span>  
 <span data-ttu-id="ae4b9-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae4b9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae4b9-116">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ae4b9-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ae4b9-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae4b9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae4b9-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae4b9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4b9-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae4b9-119">See Also</span></span>  
 [<span data-ttu-id="ae4b9-120">分析结构</span><span class="sxs-lookup"><span data-stu-id="ae4b9-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
