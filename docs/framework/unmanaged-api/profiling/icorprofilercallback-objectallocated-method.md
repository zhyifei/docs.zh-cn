---
title: ICorProfilerCallback::ObjectAllocated 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c07b37e58141f7aff747bd3772be265ae0da42ac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222011"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="330dd-102">ICorProfilerCallback::ObjectAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="330dd-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="330dd-103">通知探查器内存中堆分配的对象。</span><span class="sxs-lookup"><span data-stu-id="330dd-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="330dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="330dd-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="330dd-105">参数</span><span class="sxs-lookup"><span data-stu-id="330dd-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="330dd-106">[in]为其分配内存的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="330dd-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="330dd-107">[in]类对象的实例的 ID。</span><span class="sxs-lookup"><span data-stu-id="330dd-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="330dd-108">备注</span><span class="sxs-lookup"><span data-stu-id="330dd-108">Remarks</span></span>  
 <span data-ttu-id="330dd-109">`ObjectedAllocated`对于从堆栈或非托管的内存分配不调用方法。</span><span class="sxs-lookup"><span data-stu-id="330dd-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="330dd-110">`classId`参数可以引用尚未加载的托管代码中的类。</span><span class="sxs-lookup"><span data-stu-id="330dd-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="330dd-111">探查器将接收此类的类加载回调后立即`ObjectAllocated`回调。</span><span class="sxs-lookup"><span data-stu-id="330dd-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="330dd-112">要求</span><span class="sxs-lookup"><span data-stu-id="330dd-112">Requirements</span></span>  
 <span data-ttu-id="330dd-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="330dd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="330dd-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="330dd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="330dd-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="330dd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="330dd-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="330dd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="330dd-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="330dd-117">See also</span></span>

- [<span data-ttu-id="330dd-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="330dd-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="330dd-119">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="330dd-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="330dd-120">ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="330dd-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
