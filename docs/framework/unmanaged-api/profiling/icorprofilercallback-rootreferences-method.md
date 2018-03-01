---
title: "ICorProfilerCallback::RootReferences 方法"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd057538450deeb46a72178c725103e04a8dd126
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="33a0f-102">ICorProfilerCallback::RootReferences 方法</span><span class="sxs-lookup"><span data-stu-id="33a0f-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="33a0f-103">通知探查器包含的信息后垃圾回收根引用。</span><span class="sxs-lookup"><span data-stu-id="33a0f-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33a0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="33a0f-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33a0f-105">参数</span><span class="sxs-lookup"><span data-stu-id="33a0f-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="33a0f-106">[in]中的引用数`rootRefIds`数组。</span><span class="sxs-lookup"><span data-stu-id="33a0f-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="33a0f-107">[in]引用静态对象或在堆栈上的对象的对象 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="33a0f-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33a0f-108">备注</span><span class="sxs-lookup"><span data-stu-id="33a0f-108">Remarks</span></span>  
 <span data-ttu-id="33a0f-109">同时`RootReferences`和[icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)调用以通知探查器。</span><span class="sxs-lookup"><span data-stu-id="33a0f-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="33a0f-110">探查器通常将实现一个或另一个，但不是同时，因为传入的信息`RootReferences2`是传入的超集`RootReferences`。</span><span class="sxs-lookup"><span data-stu-id="33a0f-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="33a0f-111">之所以`rootRefIds`数组以包含 null 对象。</span><span class="sxs-lookup"><span data-stu-id="33a0f-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="33a0f-112">例如，在堆栈上声明的所有对象引用被视为根垃圾回收器，并将始终报告。</span><span class="sxs-lookup"><span data-stu-id="33a0f-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="33a0f-113">通过返回的对象 Id`RootReferences`不是有效在回调过程，因为垃圾回收可能正处于将对象从旧地址移至新的地址。</span><span class="sxs-lookup"><span data-stu-id="33a0f-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="33a0f-114">因此，探查器必须不尝试检查对象期间`RootReferences`调用。</span><span class="sxs-lookup"><span data-stu-id="33a0f-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="33a0f-115">当[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)是调用，所有对象都已移到其新位置，可以安全地检查。</span><span class="sxs-lookup"><span data-stu-id="33a0f-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33a0f-116">惠?</span><span class="sxs-lookup"><span data-stu-id="33a0f-116">Requirements</span></span>  
 <span data-ttu-id="33a0f-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33a0f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33a0f-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33a0f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33a0f-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33a0f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33a0f-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33a0f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a0f-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="33a0f-121">See Also</span></span>  
 [<span data-ttu-id="33a0f-122">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="33a0f-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
