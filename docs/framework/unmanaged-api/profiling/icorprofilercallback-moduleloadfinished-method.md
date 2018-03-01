---
title: "ICorProfilerCallback::ModuleLoadFinished 方法"
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
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 360c14ccdd67cb7609ffe2f9c49914fdda163389
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="ce83b-102">ICorProfilerCallback::ModuleLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="ce83b-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="ce83b-103">通知探查器加载已完成某个模块。</span><span class="sxs-lookup"><span data-stu-id="ce83b-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce83b-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce83b-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce83b-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce83b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ce83b-106">[in]已完成加载模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="ce83b-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="ce83b-107">[in]指示是否已成功加载了该模块的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="ce83b-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce83b-108">备注</span><span class="sxs-lookup"><span data-stu-id="ce83b-108">Remarks</span></span>  
 <span data-ttu-id="ce83b-109">值`moduleId`无效的信息请求之前，不能`ModuleLoadFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="ce83b-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="ce83b-110">加载模块的某些部分可能会继续之后`ModuleLoadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="ce83b-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="ce83b-111">失败的 HRESULT 在`hrStatus`指示失败。</span><span class="sxs-lookup"><span data-stu-id="ce83b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="ce83b-112">但是，HRESULT 为成功，在`hrStatus`仅指示已成功加载模块的第一部分。</span><span class="sxs-lookup"><span data-stu-id="ce83b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce83b-113">惠?</span><span class="sxs-lookup"><span data-stu-id="ce83b-113">Requirements</span></span>  
 <span data-ttu-id="ce83b-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce83b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce83b-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce83b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce83b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce83b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce83b-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce83b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce83b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce83b-118">See Also</span></span>  
 [<span data-ttu-id="ce83b-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ce83b-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ce83b-120">ModuleLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="ce83b-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
