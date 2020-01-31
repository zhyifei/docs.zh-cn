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
ms.openlocfilehash: 38d9e83e9fa0e9cd0586fb10a6fd79c29bead4a6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866099"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="89305-102">ICorProfilerCallback::ObjectAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="89305-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="89305-103">通知探查器已为对象分配堆中的内存。</span><span class="sxs-lookup"><span data-stu-id="89305-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89305-104">语法</span><span class="sxs-lookup"><span data-stu-id="89305-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89305-105">参数</span><span class="sxs-lookup"><span data-stu-id="89305-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="89305-106">中为其分配内存的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="89305-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="89305-107">中对象为其实例的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="89305-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89305-108">备注</span><span class="sxs-lookup"><span data-stu-id="89305-108">Remarks</span></span>  
 <span data-ttu-id="89305-109">不会为堆栈或非托管内存中的分配调用 `ObjectedAllocated` 方法。</span><span class="sxs-lookup"><span data-stu-id="89305-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="89305-110">`classId` 参数可以引用尚未加载的托管代码中的类。</span><span class="sxs-lookup"><span data-stu-id="89305-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="89305-111">探查器将在 `ObjectAllocated` 回调后立即收到该类的类加载回调。</span><span class="sxs-lookup"><span data-stu-id="89305-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89305-112">需求</span><span class="sxs-lookup"><span data-stu-id="89305-112">Requirements</span></span>  
 <span data-ttu-id="89305-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89305-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89305-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89305-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89305-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89305-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89305-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89305-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89305-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89305-117">See also</span></span>

- [<span data-ttu-id="89305-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="89305-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="89305-119">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="89305-119">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="89305-120">ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="89305-120">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
