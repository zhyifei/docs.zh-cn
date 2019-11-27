---
title: ICorProfilerCallback::RootReferences 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: 9c96cacf508ef5c056a1ff4469247393fdfb9e9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444473"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="2d444-102">ICorProfilerCallback::RootReferences 方法</span><span class="sxs-lookup"><span data-stu-id="2d444-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="2d444-103">在垃圾回收后通知探查器有关根引用的信息。</span><span class="sxs-lookup"><span data-stu-id="2d444-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d444-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d444-104">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d444-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d444-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="2d444-106">中`rootRefIds` 数组中的引用数。</span><span class="sxs-lookup"><span data-stu-id="2d444-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="2d444-107">中对象 Id 的数组，这些对象 Id 引用静态对象或堆栈上的对象。</span><span class="sxs-lookup"><span data-stu-id="2d444-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d444-108">备注</span><span class="sxs-lookup"><span data-stu-id="2d444-108">Remarks</span></span>  
 <span data-ttu-id="2d444-109">同时调用 `RootReferences` 和[ICorProfilerCallback2：： RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)来通知探查器。</span><span class="sxs-lookup"><span data-stu-id="2d444-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="2d444-110">探查器通常会实现一个或另一个，但不能同时实现两者，因为在 `RootReferences2` 中传递的信息是传入 `RootReferences`的超集。</span><span class="sxs-lookup"><span data-stu-id="2d444-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="2d444-111">`rootRefIds` 数组可以包含 null 对象。</span><span class="sxs-lookup"><span data-stu-id="2d444-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="2d444-112">例如，在堆栈上声明的所有对象引用都被垃圾回收器视为根，并将始终报告。</span><span class="sxs-lookup"><span data-stu-id="2d444-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="2d444-113">`RootReferences` 返回的对象 Id 在回调过程中无效，因为垃圾回收可能正处于将对象从旧地址移到新地址的过程中。</span><span class="sxs-lookup"><span data-stu-id="2d444-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="2d444-114">因此，探查器不能尝试在 `RootReferences` 调用过程中检查对象。</span><span class="sxs-lookup"><span data-stu-id="2d444-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="2d444-115">调用[ICorProfilerCallback2：： GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)时，所有对象已移动到它们的新位置，并且可以安全检查。</span><span class="sxs-lookup"><span data-stu-id="2d444-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d444-116">要求</span><span class="sxs-lookup"><span data-stu-id="2d444-116">Requirements</span></span>  
 <span data-ttu-id="2d444-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d444-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d444-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d444-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d444-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d444-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d444-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d444-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d444-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d444-121">See also</span></span>

- [<span data-ttu-id="2d444-122">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2d444-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
