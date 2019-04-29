---
title: COR_PRF_GC_GENERATION_RANGE 结构
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 646c4e37a7fab503a26557f9fdfc926b1186b17b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775030"
---
# <a name="corprfgcgenerationrange-structure"></a><span data-ttu-id="adcdf-102">COR_PRF_GC_GENERATION_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="adcdf-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="adcdf-103">描述一个正进行垃圾回收的内存范围（即块）。</span><span class="sxs-lookup"><span data-stu-id="adcdf-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adcdf-104">语法</span><span class="sxs-lookup"><span data-stu-id="adcdf-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="adcdf-105">成员</span><span class="sxs-lookup"><span data-stu-id="adcdf-105">Members</span></span>  
  
|<span data-ttu-id="adcdf-106">成员</span><span class="sxs-lookup"><span data-stu-id="adcdf-106">Member</span></span>|<span data-ttu-id="adcdf-107">描述</span><span class="sxs-lookup"><span data-stu-id="adcdf-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="adcdf-108">值为[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)所属枚举，用于指定向其代的内存块。</span><span class="sxs-lookup"><span data-stu-id="adcdf-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="adcdf-109">一个指定的内存块的起始位置的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="adcdf-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="adcdf-110">指向一个整数，指定的内存块 （即，在块中使用的内存量） 已使用部分大小的指针。</span><span class="sxs-lookup"><span data-stu-id="adcdf-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="adcdf-111">指向一个整数，指定内存块 （即，保留的块的内存量） 的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="adcdf-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adcdf-112">备注</span><span class="sxs-lookup"><span data-stu-id="adcdf-112">Remarks</span></span>  
 <span data-ttu-id="adcdf-113">`rangeLength`保证值为准确起见仅当[ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)或[ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)，这两个可使用该技术`COR_PRF_GC_GENERATION_RANGE`结构，请从调用[ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)或[ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="adcdf-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adcdf-114">要求</span><span class="sxs-lookup"><span data-stu-id="adcdf-114">Requirements</span></span>  
 <span data-ttu-id="adcdf-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="adcdf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adcdf-116">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="adcdf-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="adcdf-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adcdf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adcdf-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adcdf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adcdf-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="adcdf-119">See also</span></span>

- [<span data-ttu-id="adcdf-120">分析结构</span><span class="sxs-lookup"><span data-stu-id="adcdf-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
