---
title: ICorProfilerCallback::ModuleLoadStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b847cbbdf1bfccd91ca212dadd1fcd82cc12c82
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768198"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="5ca47-102">ICorProfilerCallback::ModuleLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="5ca47-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="5ca47-103">通知探查器正在加载的模块。</span><span class="sxs-lookup"><span data-stu-id="5ca47-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ca47-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ca47-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ca47-105">参数</span><span class="sxs-lookup"><span data-stu-id="5ca47-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5ca47-106">[in]正在加载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="5ca47-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ca47-107">备注</span><span class="sxs-lookup"><span data-stu-id="5ca47-107">Remarks</span></span>  
 <span data-ttu-id="5ca47-108">值`moduleId`不是有效的信息请求之前[icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)调用方法。</span><span class="sxs-lookup"><span data-stu-id="5ca47-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ca47-109">要求</span><span class="sxs-lookup"><span data-stu-id="5ca47-109">Requirements</span></span>  
 <span data-ttu-id="5ca47-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5ca47-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ca47-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ca47-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ca47-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ca47-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ca47-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ca47-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca47-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ca47-114">See also</span></span>

- [<span data-ttu-id="5ca47-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="5ca47-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
