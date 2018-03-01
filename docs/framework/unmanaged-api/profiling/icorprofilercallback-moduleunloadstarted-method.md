---
title: "ICorProfilerCallback::ModuleUnloadStarted 方法"
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
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 384d655254cc79283f93ff2e608b0429c4a84ae8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="06323-102">ICorProfilerCallback::ModuleUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="06323-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="06323-103">通知探查器正在卸载模块。</span><span class="sxs-lookup"><span data-stu-id="06323-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06323-104">语法</span><span class="sxs-lookup"><span data-stu-id="06323-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="06323-105">参数</span><span class="sxs-lookup"><span data-stu-id="06323-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="06323-106">[in]正在卸载模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="06323-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06323-107">备注</span><span class="sxs-lookup"><span data-stu-id="06323-107">Remarks</span></span>  
 <span data-ttu-id="06323-108">值`moduleId`无效的信息请求后，不能`ModuleUnloadStarted`方法返回-这是探查器的最后一次机会，若要获取有关此模块的信息。</span><span class="sxs-lookup"><span data-stu-id="06323-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06323-109">惠?</span><span class="sxs-lookup"><span data-stu-id="06323-109">Requirements</span></span>  
 <span data-ttu-id="06323-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06323-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06323-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06323-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06323-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06323-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06323-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06323-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06323-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="06323-114">See Also</span></span>  
 [<span data-ttu-id="06323-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="06323-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="06323-116">ModuleUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="06323-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
