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
ms.openlocfilehash: efd08eedf6812a46a46135eaa6f0089257f0a209
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="baf02-102">ICorProfilerCallback::FunctionUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="baf02-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="baf02-103">通知探查器运行时已开始卸载某个函数。</span><span class="sxs-lookup"><span data-stu-id="baf02-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf02-104">语法</span><span class="sxs-lookup"><span data-stu-id="baf02-104">Syntax</span></span>  
  
```  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="baf02-105">参数</span><span class="sxs-lookup"><span data-stu-id="baf02-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="baf02-106">[in]正在卸载模块的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="baf02-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baf02-107">备注</span><span class="sxs-lookup"><span data-stu-id="baf02-107">Remarks</span></span>  
 <span data-ttu-id="baf02-108">值`functionId`参数将不再有效之后此方法返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="baf02-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf02-109">要求</span><span class="sxs-lookup"><span data-stu-id="baf02-109">Requirements</span></span>  
 <span data-ttu-id="baf02-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="baf02-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf02-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="baf02-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="baf02-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baf02-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baf02-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf02-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf02-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="baf02-114">See Also</span></span>  
 [<span data-ttu-id="baf02-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="baf02-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
