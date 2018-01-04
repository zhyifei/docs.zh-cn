---
title: "ICorProfilerCallback::FunctionUnloadStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.FunctionUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 957b5a89dbb3e780b0e5512afe405e669fdbecce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="c274b-102">ICorProfilerCallback::FunctionUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="c274b-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="c274b-103">通知探查器运行时已开始卸载某个函数。</span><span class="sxs-lookup"><span data-stu-id="c274b-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c274b-104">语法</span><span class="sxs-lookup"><span data-stu-id="c274b-104">Syntax</span></span>  
  
```  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="c274b-105">参数</span><span class="sxs-lookup"><span data-stu-id="c274b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c274b-106">[in]正在卸载模块的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="c274b-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c274b-107">备注</span><span class="sxs-lookup"><span data-stu-id="c274b-107">Remarks</span></span>  
 <span data-ttu-id="c274b-108">值`functionId`参数将不再有效之后此方法返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="c274b-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c274b-109">惠?</span><span class="sxs-lookup"><span data-stu-id="c274b-109">Requirements</span></span>  
 <span data-ttu-id="c274b-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c274b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c274b-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c274b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c274b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c274b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c274b-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c274b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c274b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c274b-114">See Also</span></span>  
 [<span data-ttu-id="c274b-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c274b-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
