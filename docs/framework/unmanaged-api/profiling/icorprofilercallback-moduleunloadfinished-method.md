---
title: "ICorProfilerCallback::ModuleUnloadFinished 方法"
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
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6f9f048d60d2d463e3d846fadda91932a9a2a091
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="bdc70-102">ICorProfilerCallback::ModuleUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="bdc70-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="bdc70-103">通知探查器已完成某个模块的卸载。</span><span class="sxs-lookup"><span data-stu-id="bdc70-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdc70-104">语法</span><span class="sxs-lookup"><span data-stu-id="bdc70-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bdc70-105">参数</span><span class="sxs-lookup"><span data-stu-id="bdc70-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="bdc70-106">[in]已卸载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="bdc70-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bdc70-107">[in]一个 HRESULT，指示是否已成功模块已被卸载。</span><span class="sxs-lookup"><span data-stu-id="bdc70-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdc70-108">备注</span><span class="sxs-lookup"><span data-stu-id="bdc70-108">Remarks</span></span>  
 <span data-ttu-id="bdc70-109">值`moduleId`无效的信息请求后，不能[icorprofilercallback:: Moduleunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="bdc70-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="bdc70-110">卸载类的某些部分可能会继续之后`ModuleUnloadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="bdc70-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="bdc70-111">失败的 HRESULT 在`hrStatus`指示失败。</span><span class="sxs-lookup"><span data-stu-id="bdc70-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bdc70-112">但是，HRESULT 为成功，在`hrStatus`仅指示已成功卸载该模块的第一部分。</span><span class="sxs-lookup"><span data-stu-id="bdc70-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdc70-113">惠?</span><span class="sxs-lookup"><span data-stu-id="bdc70-113">Requirements</span></span>  
 <span data-ttu-id="bdc70-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bdc70-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdc70-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bdc70-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bdc70-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdc70-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdc70-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdc70-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc70-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdc70-118">See Also</span></span>  
 [<span data-ttu-id="bdc70-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="bdc70-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
