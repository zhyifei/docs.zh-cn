---
title: ICorProfilerCallback::ObjectReferences 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4141c79502dae89ec228e4e39da121615f292786
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782974"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="c9c5a-102">ICorProfilerCallback::ObjectReferences 方法</span><span class="sxs-lookup"><span data-stu-id="c9c5a-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="c9c5a-103">通知有关指定的对象引用的对象的内存探查器。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9c5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9c5a-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9c5a-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9c5a-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="c9c5a-106">[in]所引用对象的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="c9c5a-107">[in]指定的对象的实例的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="c9c5a-108">[in]将指定的对象引用的对象数 (即中的元素数`objectRefIds`数组)。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="c9c5a-109">[in]被引用的对象 Id 的数组`objectId`。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9c5a-110">备注</span><span class="sxs-lookup"><span data-stu-id="c9c5a-110">Remarks</span></span>  
 <span data-ttu-id="c9c5a-111">`ObjectReferences`完成垃圾回收后保留在堆中每个对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="c9c5a-112">如果探查器从此回调返回错误，将停止分析服务下, 一次垃圾回收之前调用此回调。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="c9c5a-113">`ObjectReferences`可以结合使用回调[icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)回调来创建运行时的完整的对象引用关系图。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="c9c5a-114">公共语言运行时 (CLR) 可确保每个对象引用一次报告的`ObjectReferences`方法。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="c9c5a-115">通过返回的对象 Id`ObjectReferences`不能在该回调本身，因为垃圾回收可能正处于移动对象。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="c9c5a-116">因此，探查器必须不尝试检查对象在`ObjectReferences`调用。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="c9c5a-117">当[ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)调用时，垃圾收集完毕且可以安全地完成检查。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="c9c5a-118">为空`ClassId`指示`objectId`正在卸载的类型。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9c5a-119">要求</span><span class="sxs-lookup"><span data-stu-id="c9c5a-119">Requirements</span></span>  
 <span data-ttu-id="c9c5a-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9c5a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9c5a-121">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c9c5a-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c9c5a-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9c5a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9c5a-123">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9c5a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c5a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9c5a-124">See also</span></span>

- [<span data-ttu-id="c9c5a-125">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c9c5a-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
