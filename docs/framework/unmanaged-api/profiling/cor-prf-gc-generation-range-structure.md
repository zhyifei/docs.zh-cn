---
title: "COR_PRF_GC_GENERATION_RANGE 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59969f45d4cca0ff208bd9e77c93994cad61ab13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcgenerationrange-structure"></a><span data-ttu-id="77f43-102">COR_PRF_GC_GENERATION_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="77f43-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="77f43-103">描述一个正进行垃圾回收的内存范围（即块）。</span><span class="sxs-lookup"><span data-stu-id="77f43-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77f43-104">语法</span><span class="sxs-lookup"><span data-stu-id="77f43-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="77f43-105">成员</span><span class="sxs-lookup"><span data-stu-id="77f43-105">Members</span></span>  
  
|<span data-ttu-id="77f43-106">成员</span><span class="sxs-lookup"><span data-stu-id="77f43-106">Member</span></span>|<span data-ttu-id="77f43-107">描述</span><span class="sxs-lookup"><span data-stu-id="77f43-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="77f43-108">值为[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)所属指定的内存块的与其生成的枚举。</span><span class="sxs-lookup"><span data-stu-id="77f43-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="77f43-109">一个指定的内存块的起始位置的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="77f43-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="77f43-110">指向一个整数，指定的内存块 （即，在块中使用的内存量） 已使用部分大小的指针。</span><span class="sxs-lookup"><span data-stu-id="77f43-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="77f43-111">指向一个整数，指定内存块 （即块保留的内存量） 的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="77f43-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77f43-112">备注</span><span class="sxs-lookup"><span data-stu-id="77f43-112">Remarks</span></span>  
 <span data-ttu-id="77f43-113">`rangeLength`值一定要准确才[icorprofilerinfo2:: Getgenerationbounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)或[icorprofilerinfo2:: Getobjectgeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)，这两个使用`COR_PRF_GC_GENERATION_RANGE`结构，请从调用[icorprofilercallback2:: Garbagecollectionstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)或[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="77f43-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77f43-114">惠?</span><span class="sxs-lookup"><span data-stu-id="77f43-114">Requirements</span></span>  
 <span data-ttu-id="77f43-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77f43-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77f43-116">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="77f43-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="77f43-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77f43-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77f43-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77f43-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f43-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="77f43-119">See Also</span></span>  
 [<span data-ttu-id="77f43-120">分析结构</span><span class="sxs-lookup"><span data-stu-id="77f43-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
