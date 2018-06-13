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
ms.openlocfilehash: e64eeff8ef80aa264c9c49bd12a0cc45e0da18a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461882"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="9ed47-102">ICorProfilerCallback::ObjectReferences 方法</span><span class="sxs-lookup"><span data-stu-id="9ed47-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="9ed47-103">通知探查器在内存中由指定的对象引用的对象有关。</span><span class="sxs-lookup"><span data-stu-id="9ed47-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed47-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ed47-104">Syntax</span></span>  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ed47-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ed47-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="9ed47-106">[in]引用对象的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="9ed47-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="9ed47-107">[in]类的指定的对象的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="9ed47-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="9ed47-108">[in]由指定的对象引用的对象的数目 (即中的元素数`objectRefIds`数组)。</span><span class="sxs-lookup"><span data-stu-id="9ed47-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="9ed47-109">[in]被引用的对象的 Id 的数组， `objectId`。</span><span class="sxs-lookup"><span data-stu-id="9ed47-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ed47-110">备注</span><span class="sxs-lookup"><span data-stu-id="9ed47-110">Remarks</span></span>  
 <span data-ttu-id="9ed47-111">`ObjectReferences`针对每个垃圾回收完成后，为堆中剩余的对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="9ed47-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="9ed47-112">如果探查器从此回调返回错误，则将停止分析服务下, 一次垃圾回收之前调用此回调。</span><span class="sxs-lookup"><span data-stu-id="9ed47-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="9ed47-113">`ObjectReferences`可结合使用回调[icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)回调来创建运行时的完整的对象引用关系图。</span><span class="sxs-lookup"><span data-stu-id="9ed47-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="9ed47-114">公共语言运行时 (CLR) 可确保每个对象引用一次报告的`ObjectReferences`方法。</span><span class="sxs-lookup"><span data-stu-id="9ed47-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="9ed47-115">通过返回的对象 Id`ObjectReferences`不是有效在回调过程，因为垃圾回收可能正处于将对象移。</span><span class="sxs-lookup"><span data-stu-id="9ed47-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="9ed47-116">因此，探查器必须不尝试检查对象期间`ObjectReferences`调用。</span><span class="sxs-lookup"><span data-stu-id="9ed47-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="9ed47-117">当[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)调用时，垃圾回收完成集合并检查，可以安全地进行。</span><span class="sxs-lookup"><span data-stu-id="9ed47-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="9ed47-118">Null`ClassId`指示`objectId`具有正在卸载的类型。</span><span class="sxs-lookup"><span data-stu-id="9ed47-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ed47-119">要求</span><span class="sxs-lookup"><span data-stu-id="9ed47-119">Requirements</span></span>  
 <span data-ttu-id="9ed47-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ed47-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ed47-121">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ed47-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ed47-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ed47-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ed47-123">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ed47-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed47-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ed47-124">See Also</span></span>  
 [<span data-ttu-id="9ed47-125">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9ed47-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
