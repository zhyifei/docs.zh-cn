---
title: "ICorProfilerCallback2::GarbageCollectionFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 287c33a80144b9b04fd7e0797071d40e46a52454
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="142eb-102">ICorProfilerCallback2::GarbageCollectionFinished 方法</span><span class="sxs-lookup"><span data-stu-id="142eb-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="142eb-103">垃圾回收已完成，并且为其颁发的所有垃圾回收回调通知探查器。</span><span class="sxs-lookup"><span data-stu-id="142eb-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="142eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="142eb-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="142eb-105">备注</span><span class="sxs-lookup"><span data-stu-id="142eb-105">Remarks</span></span>  
 <span data-ttu-id="142eb-106">它是安全的探查器检查其最终位置中的对象时`GarbageCollectionFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="142eb-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="142eb-107">要求</span><span class="sxs-lookup"><span data-stu-id="142eb-107">Requirements</span></span>  
 <span data-ttu-id="142eb-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="142eb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="142eb-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="142eb-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="142eb-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="142eb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="142eb-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="142eb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142eb-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="142eb-112">See Also</span></span>  
 [<span data-ttu-id="142eb-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="142eb-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="142eb-114">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="142eb-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
