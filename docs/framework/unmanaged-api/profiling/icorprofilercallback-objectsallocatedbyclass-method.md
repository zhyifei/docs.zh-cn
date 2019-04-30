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
ms.openlocfilehash: b9f5d2c08abbcab6bc1a6d0569b8e70d7c919def
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041907"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="98170-102">ICorProfilerCallback::ObjectsAllocatedByClass 方法</span><span class="sxs-lookup"><span data-stu-id="98170-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="98170-103">通知探查器有关的最新的垃圾回收以来已创建的每个指定的类的实例数。</span><span class="sxs-lookup"><span data-stu-id="98170-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98170-104">语法</span><span class="sxs-lookup"><span data-stu-id="98170-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="98170-105">参数</span><span class="sxs-lookup"><span data-stu-id="98170-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="98170-106">[in]大小`classIds`和`cObjects`数组。</span><span class="sxs-lookup"><span data-stu-id="98170-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="98170-107">[in]类 Id，其中每个 ID 指定的类具有一个或多个实例的数组。</span><span class="sxs-lookup"><span data-stu-id="98170-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="98170-108">[in]一个整数，其中每个整数指定中的相应类的实例数数组`classIds`数组。</span><span class="sxs-lookup"><span data-stu-id="98170-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98170-109">备注</span><span class="sxs-lookup"><span data-stu-id="98170-109">Remarks</span></span>  
 <span data-ttu-id="98170-110">`classIds`和`cObjects`数组是并行数组。</span><span class="sxs-lookup"><span data-stu-id="98170-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="98170-111">例如，`classIds[i]`和`cObjects[i]`引用同一个类。</span><span class="sxs-lookup"><span data-stu-id="98170-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="98170-112">如果自上次垃圾回收以来创建的类没有实例，则省略类。</span><span class="sxs-lookup"><span data-stu-id="98170-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="98170-113">`ObjectsAllocatedByClass`回调不会报告大型对象堆中分配的对象。</span><span class="sxs-lookup"><span data-stu-id="98170-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="98170-114">通过报告的数字`ObjectsAllocatedByClass`只是估计。</span><span class="sxs-lookup"><span data-stu-id="98170-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="98170-115">对于精确计数，请使用[icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)。</span><span class="sxs-lookup"><span data-stu-id="98170-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="98170-116">`classIds`数组可能包含一个或多个 null 项，如果相应`cObjects`数组具有正在卸载的类型。</span><span class="sxs-lookup"><span data-stu-id="98170-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98170-117">要求</span><span class="sxs-lookup"><span data-stu-id="98170-117">Requirements</span></span>  
 <span data-ttu-id="98170-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98170-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98170-119">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="98170-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="98170-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98170-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98170-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98170-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98170-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="98170-122">See also</span></span>

- [<span data-ttu-id="98170-123">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="98170-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
