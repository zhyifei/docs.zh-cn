---
title: "ICorProfilerCallback::ObjectAllocated 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectAllocated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a7e67e6085db4b73ca39688935767072ceadb68e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="363eb-102">ICorProfilerCallback::ObjectAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="363eb-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="363eb-103">通知探查器在堆的内存已分配对象。</span><span class="sxs-lookup"><span data-stu-id="363eb-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="363eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="363eb-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="363eb-105">参数</span><span class="sxs-lookup"><span data-stu-id="363eb-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="363eb-106">[in]为其分配内存的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="363eb-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="363eb-107">[in]对象的实例的类 ID。</span><span class="sxs-lookup"><span data-stu-id="363eb-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="363eb-108">备注</span><span class="sxs-lookup"><span data-stu-id="363eb-108">Remarks</span></span>  
 <span data-ttu-id="363eb-109">`ObjectedAllocated`方法不会为从堆栈或非托管的内存中分配的调用。</span><span class="sxs-lookup"><span data-stu-id="363eb-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="363eb-110">`classId`参数可以引用尚未加载的托管代码中的类。</span><span class="sxs-lookup"><span data-stu-id="363eb-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="363eb-111">探查器会收到为该类的类负载回调后立即`ObjectAllocated`回调。</span><span class="sxs-lookup"><span data-stu-id="363eb-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="363eb-112">要求</span><span class="sxs-lookup"><span data-stu-id="363eb-112">Requirements</span></span>  
 <span data-ttu-id="363eb-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="363eb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="363eb-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="363eb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="363eb-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="363eb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="363eb-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="363eb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="363eb-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="363eb-117">See Also</span></span>  
 [<span data-ttu-id="363eb-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="363eb-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="363eb-119">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="363eb-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)  
 [<span data-ttu-id="363eb-120">ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="363eb-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
