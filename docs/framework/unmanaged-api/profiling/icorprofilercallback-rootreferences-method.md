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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cfab1d716b5a8b530561e2dc72442591eb0d8e42
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499025"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="bbb26-102">ICorProfilerCallback::RootReferences 方法</span><span class="sxs-lookup"><span data-stu-id="bbb26-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="bbb26-103">通知探查器与垃圾回收后根引用的信息。</span><span class="sxs-lookup"><span data-stu-id="bbb26-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbb26-104">语法</span><span class="sxs-lookup"><span data-stu-id="bbb26-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbb26-105">参数</span><span class="sxs-lookup"><span data-stu-id="bbb26-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="bbb26-106">[in]中的引用数`rootRefIds`数组。</span><span class="sxs-lookup"><span data-stu-id="bbb26-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="bbb26-107">[in]一个对象 Id 引用静态对象或在堆栈上的对象的数组。</span><span class="sxs-lookup"><span data-stu-id="bbb26-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbb26-108">备注</span><span class="sxs-lookup"><span data-stu-id="bbb26-108">Remarks</span></span>  
 <span data-ttu-id="bbb26-109">这两`RootReferences`并[ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)调用以通知探查器。</span><span class="sxs-lookup"><span data-stu-id="bbb26-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="bbb26-110">探查器通常会实现一个或另一个，但不是同时，因为传入的信息`RootReferences2`是传入的超集`RootReferences`。</span><span class="sxs-lookup"><span data-stu-id="bbb26-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="bbb26-111">很可能`rootRefIds`数组以包含 null 对象。</span><span class="sxs-lookup"><span data-stu-id="bbb26-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="bbb26-112">例如，在堆栈上声明的所有对象引用被视为根的垃圾回收器，并将始终报告。</span><span class="sxs-lookup"><span data-stu-id="bbb26-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="bbb26-113">通过返回的对象 Id`RootReferences`不能在该回调本身，因为垃圾回收可能正处于将对象从旧地址移到新的地址。</span><span class="sxs-lookup"><span data-stu-id="bbb26-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="bbb26-114">因此，探查器必须不尝试检查对象在`RootReferences`调用。</span><span class="sxs-lookup"><span data-stu-id="bbb26-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="bbb26-115">当[ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)是调用，所有对象都已移到其新位置并且可以安全地检查。</span><span class="sxs-lookup"><span data-stu-id="bbb26-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbb26-116">要求</span><span class="sxs-lookup"><span data-stu-id="bbb26-116">Requirements</span></span>  
 <span data-ttu-id="bbb26-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb26-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbb26-118">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bbb26-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bbb26-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbb26-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbb26-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbb26-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb26-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbb26-121">See also</span></span>
- [<span data-ttu-id="bbb26-122">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="bbb26-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
