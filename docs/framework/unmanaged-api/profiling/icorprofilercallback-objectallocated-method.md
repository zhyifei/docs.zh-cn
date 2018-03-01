---
title: "ICorProfilerCallback::ObjectAllocated 方法"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 37f4701271f299698d7cd323b7d701f4cb7adb25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="81dcc-102">ICorProfilerCallback::ObjectAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="81dcc-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="81dcc-103">通知探查器在堆的内存已分配对象。</span><span class="sxs-lookup"><span data-stu-id="81dcc-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81dcc-104">语法</span><span class="sxs-lookup"><span data-stu-id="81dcc-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81dcc-105">参数</span><span class="sxs-lookup"><span data-stu-id="81dcc-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="81dcc-106">[in]为其分配内存的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="81dcc-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="81dcc-107">[in]对象的实例的类 ID。</span><span class="sxs-lookup"><span data-stu-id="81dcc-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81dcc-108">备注</span><span class="sxs-lookup"><span data-stu-id="81dcc-108">Remarks</span></span>  
 <span data-ttu-id="81dcc-109">`ObjectedAllocated`方法不会为从堆栈或非托管的内存中分配的调用。</span><span class="sxs-lookup"><span data-stu-id="81dcc-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="81dcc-110">`classId`参数可以引用尚未加载的托管代码中的类。</span><span class="sxs-lookup"><span data-stu-id="81dcc-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="81dcc-111">探查器会收到为该类的类负载回调后立即`ObjectAllocated`回调。</span><span class="sxs-lookup"><span data-stu-id="81dcc-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81dcc-112">惠?</span><span class="sxs-lookup"><span data-stu-id="81dcc-112">Requirements</span></span>  
 <span data-ttu-id="81dcc-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81dcc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81dcc-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81dcc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81dcc-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81dcc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81dcc-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81dcc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81dcc-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="81dcc-117">See Also</span></span>  
 [<span data-ttu-id="81dcc-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="81dcc-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="81dcc-119">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="81dcc-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)  
 [<span data-ttu-id="81dcc-120">ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="81dcc-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
