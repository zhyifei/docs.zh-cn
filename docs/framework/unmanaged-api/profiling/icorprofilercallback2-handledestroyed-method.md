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
ms.openlocfilehash: 3cb8783ba1427ecc2396abb32f350664ddf83d19
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779312"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="c36af-102">ICorProfilerCallback2::HandleDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="c36af-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="c36af-103">通知垃圾回收句柄已被销毁代码探查器。</span><span class="sxs-lookup"><span data-stu-id="c36af-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36af-104">语法</span><span class="sxs-lookup"><span data-stu-id="c36af-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c36af-105">参数</span><span class="sxs-lookup"><span data-stu-id="c36af-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="c36af-106">[in]垃圾回收的句柄的 ID。</span><span class="sxs-lookup"><span data-stu-id="c36af-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c36af-107">要求</span><span class="sxs-lookup"><span data-stu-id="c36af-107">Requirements</span></span>  
 <span data-ttu-id="c36af-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c36af-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c36af-109">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c36af-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c36af-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c36af-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c36af-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c36af-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36af-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c36af-112">See also</span></span>

- [<span data-ttu-id="c36af-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c36af-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c36af-114">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="c36af-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
