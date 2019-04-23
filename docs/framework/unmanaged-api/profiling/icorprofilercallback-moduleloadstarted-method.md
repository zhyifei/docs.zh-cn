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
ms.openlocfilehash: 3503aa1eb86246365e31f52313893ad8713f5748
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153681"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="20533-102">ICorProfilerCallback::ModuleLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="20533-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="20533-103">通知探查器正在加载的模块。</span><span class="sxs-lookup"><span data-stu-id="20533-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20533-104">语法</span><span class="sxs-lookup"><span data-stu-id="20533-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20533-105">参数</span><span class="sxs-lookup"><span data-stu-id="20533-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="20533-106">[in]正在加载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="20533-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20533-107">备注</span><span class="sxs-lookup"><span data-stu-id="20533-107">Remarks</span></span>  
 <span data-ttu-id="20533-108">值`moduleId`不是有效的信息请求之前[icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)调用方法。</span><span class="sxs-lookup"><span data-stu-id="20533-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20533-109">要求</span><span class="sxs-lookup"><span data-stu-id="20533-109">Requirements</span></span>  
 <span data-ttu-id="20533-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20533-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20533-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20533-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20533-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20533-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20533-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20533-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20533-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="20533-114">See also</span></span>

- [<span data-ttu-id="20533-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="20533-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
