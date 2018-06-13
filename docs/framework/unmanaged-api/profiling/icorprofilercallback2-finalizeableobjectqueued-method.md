---
title: ICorProfilerCallback2::FinalizeableObjectQueued 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4d10b313adc60e2b851d32aeea70e2993480b0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451803"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="904d7-102">ICorProfilerCallback2::FinalizeableObjectQueued 方法</span><span class="sxs-lookup"><span data-stu-id="904d7-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="904d7-103">通知代码探查器已排队具有终结器的对象发送至终结器线程的执行其`Finalize`方法。</span><span class="sxs-lookup"><span data-stu-id="904d7-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="904d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="904d7-104">Syntax</span></span>  
  
```  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="904d7-105">参数</span><span class="sxs-lookup"><span data-stu-id="904d7-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="904d7-106">[in]值为[COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)描述的终结器方面的枚举。</span><span class="sxs-lookup"><span data-stu-id="904d7-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="904d7-107">[in]已在排队等候的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="904d7-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="904d7-108">要求</span><span class="sxs-lookup"><span data-stu-id="904d7-108">Requirements</span></span>  
 <span data-ttu-id="904d7-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="904d7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="904d7-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="904d7-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="904d7-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="904d7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="904d7-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="904d7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="904d7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="904d7-113">See Also</span></span>  
 [<span data-ttu-id="904d7-114">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="904d7-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="904d7-115">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="904d7-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
