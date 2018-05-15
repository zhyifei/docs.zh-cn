---
title: ICorProfilerCallback::ObjectsAllocatedByClass 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78dde5c50666333c02c8c1a9a167e17af3f40341
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="03d6b-102">ICorProfilerCallback::ObjectsAllocatedByClass 方法</span><span class="sxs-lookup"><span data-stu-id="03d6b-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="03d6b-103">通知探查器有关的最新的垃圾回收后，创建的每个指定的类的实例数。</span><span class="sxs-lookup"><span data-stu-id="03d6b-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03d6b-104">语法</span><span class="sxs-lookup"><span data-stu-id="03d6b-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03d6b-105">参数</span><span class="sxs-lookup"><span data-stu-id="03d6b-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="03d6b-106">[in]大小`classIds`和`cObjects`数组。</span><span class="sxs-lookup"><span data-stu-id="03d6b-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="03d6b-107">[in]类 Id，其中每个 ID 指定的类具有一个或多个实例的数组。</span><span class="sxs-lookup"><span data-stu-id="03d6b-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="03d6b-108">[in]一个整数，其中每个整数指定中的对应类的实例数数组`classIds`数组。</span><span class="sxs-lookup"><span data-stu-id="03d6b-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03d6b-109">备注</span><span class="sxs-lookup"><span data-stu-id="03d6b-109">Remarks</span></span>  
 <span data-ttu-id="03d6b-110">`classIds`和`cObjects`数组是并行数组。</span><span class="sxs-lookup"><span data-stu-id="03d6b-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="03d6b-111">例如，`classIds[i]`和`cObjects[i]`引用同一个类。</span><span class="sxs-lookup"><span data-stu-id="03d6b-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="03d6b-112">如果自上次垃圾回收后不创建了一个类的任何实例，则忽略该类。</span><span class="sxs-lookup"><span data-stu-id="03d6b-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="03d6b-113">`ObjectsAllocatedByClass`回调不会报告大对象堆中分配的对象。</span><span class="sxs-lookup"><span data-stu-id="03d6b-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="03d6b-114">报告的数目`ObjectsAllocatedByClass`只是估计。</span><span class="sxs-lookup"><span data-stu-id="03d6b-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="03d6b-115">精确计数，使用[icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)。</span><span class="sxs-lookup"><span data-stu-id="03d6b-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="03d6b-116">`classIds`数组可能包含一个或多个 null 条目，如果相应`cObjects`数组具有要卸载的类型。</span><span class="sxs-lookup"><span data-stu-id="03d6b-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03d6b-117">要求</span><span class="sxs-lookup"><span data-stu-id="03d6b-117">Requirements</span></span>  
 <span data-ttu-id="03d6b-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="03d6b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03d6b-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="03d6b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="03d6b-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03d6b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03d6b-121">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03d6b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d6b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="03d6b-122">See Also</span></span>  
 [<span data-ttu-id="03d6b-123">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="03d6b-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
