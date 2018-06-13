---
title: ICorProfilerCallback2::HandleDestroyed 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31492711ea9927c07f611ff9ec9bbe49d4857d46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451956"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="929e8-102">ICorProfilerCallback2::HandleDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="929e8-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="929e8-103">通知垃圾回收句柄已销毁代码探查器。</span><span class="sxs-lookup"><span data-stu-id="929e8-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="929e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="929e8-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="929e8-105">参数</span><span class="sxs-lookup"><span data-stu-id="929e8-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="929e8-106">[in]垃圾回收句柄的 ID。</span><span class="sxs-lookup"><span data-stu-id="929e8-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="929e8-107">要求</span><span class="sxs-lookup"><span data-stu-id="929e8-107">Requirements</span></span>  
 <span data-ttu-id="929e8-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="929e8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="929e8-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="929e8-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="929e8-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="929e8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="929e8-111">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="929e8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929e8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="929e8-112">See Also</span></span>  
 [<span data-ttu-id="929e8-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="929e8-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="929e8-114">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="929e8-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
