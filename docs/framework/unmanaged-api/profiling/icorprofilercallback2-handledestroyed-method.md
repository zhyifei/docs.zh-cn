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
ms.openlocfilehash: bc6b086b444a769afbf01369b50c69e242a21050
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090480"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="4e000-102">ICorProfilerCallback2::HandleDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="4e000-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="4e000-103">通知垃圾回收句柄已被销毁代码探查器。</span><span class="sxs-lookup"><span data-stu-id="4e000-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e000-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e000-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e000-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e000-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="4e000-106">[in]垃圾回收的句柄的 ID。</span><span class="sxs-lookup"><span data-stu-id="4e000-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e000-107">要求</span><span class="sxs-lookup"><span data-stu-id="4e000-107">Requirements</span></span>  
 <span data-ttu-id="4e000-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e000-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e000-109">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e000-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e000-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e000-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4e000-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="4e000-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4e000-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e000-112">See also</span></span>

- [<span data-ttu-id="4e000-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4e000-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4e000-114">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="4e000-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
