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
ms.openlocfilehash: 9ba021ec223d00e57081567b76f70f59768e6b9a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445868"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="8d20e-102">ICorProfilerCallback::ObjectsAllocatedByClass 方法</span><span class="sxs-lookup"><span data-stu-id="8d20e-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="8d20e-103">通知探查器自最近一次垃圾回收后已创建的每个指定类的实例数。</span><span class="sxs-lookup"><span data-stu-id="8d20e-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d20e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d20e-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d20e-105">参数</span><span class="sxs-lookup"><span data-stu-id="8d20e-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="8d20e-106">中`classIds` 和 `cObjects` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="8d20e-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="8d20e-107">中类 Id 的数组，其中每个 ID 指定一个包含一个或多个实例的类。</span><span class="sxs-lookup"><span data-stu-id="8d20e-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="8d20e-108">中一个整数数组，其中每个整数指定 `classIds` 数组中相应类的实例数。</span><span class="sxs-lookup"><span data-stu-id="8d20e-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d20e-109">备注</span><span class="sxs-lookup"><span data-stu-id="8d20e-109">Remarks</span></span>  
 <span data-ttu-id="8d20e-110">`classIds` 和 `cObjects` 数组是并行数组。</span><span class="sxs-lookup"><span data-stu-id="8d20e-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="8d20e-111">例如，`classIds[i]` 和 `cObjects[i]` 引用相同的类。</span><span class="sxs-lookup"><span data-stu-id="8d20e-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="8d20e-112">如果自上次垃圾回收后未创建类的任何实例，则忽略类。</span><span class="sxs-lookup"><span data-stu-id="8d20e-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="8d20e-113">`ObjectsAllocatedByClass` 回调不会报告在大型对象堆中分配的对象。</span><span class="sxs-lookup"><span data-stu-id="8d20e-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="8d20e-114">`ObjectsAllocatedByClass` 报告的数字仅为估算值。</span><span class="sxs-lookup"><span data-stu-id="8d20e-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="8d20e-115">对于确切计数，请使用[ICorProfilerCallback：： ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)。</span><span class="sxs-lookup"><span data-stu-id="8d20e-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="8d20e-116">如果相应的 `cObjects` 数组包含正在卸载的类型，则 `classIds` 数组可能包含一个或多个 null 项。</span><span class="sxs-lookup"><span data-stu-id="8d20e-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d20e-117">要求</span><span class="sxs-lookup"><span data-stu-id="8d20e-117">Requirements</span></span>  
 <span data-ttu-id="8d20e-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d20e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d20e-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d20e-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d20e-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d20e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d20e-121">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d20e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d20e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d20e-122">See also</span></span>

- [<span data-ttu-id="8d20e-123">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="8d20e-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
