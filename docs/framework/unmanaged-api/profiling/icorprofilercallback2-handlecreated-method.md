---
title: "ICorProfilerCallback2::HandleCreated 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.HandleCreated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d866261f16e344f6842ba59e83424219ec3d8dfb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="e91d7-102">ICorProfilerCallback2::HandleCreated 方法</span><span class="sxs-lookup"><span data-stu-id="e91d7-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="e91d7-103">通知代码探查器已创建了垃圾回收句柄。</span><span class="sxs-lookup"><span data-stu-id="e91d7-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e91d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="e91d7-104">Syntax</span></span>  
  
```  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e91d7-105">参数</span><span class="sxs-lookup"><span data-stu-id="e91d7-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="e91d7-106">[in]垃圾回收句柄的 ID。</span><span class="sxs-lookup"><span data-stu-id="e91d7-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="e91d7-107">[in]为其创建垃圾回收句柄的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="e91d7-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e91d7-108">要求</span><span class="sxs-lookup"><span data-stu-id="e91d7-108">Requirements</span></span>  
 <span data-ttu-id="e91d7-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e91d7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e91d7-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e91d7-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e91d7-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e91d7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e91d7-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e91d7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91d7-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e91d7-113">See Also</span></span>  
 [<span data-ttu-id="e91d7-114">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e91d7-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="e91d7-115">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="e91d7-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
