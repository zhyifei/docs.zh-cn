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
ms.openlocfilehash: 88da5a968bf224dc5b6f45ee5d1d2e75386086f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866151"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="2a819-102">ICorProfilerCallback::ModuleLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="2a819-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="2a819-103">通知探查器正在加载模块。</span><span class="sxs-lookup"><span data-stu-id="2a819-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a819-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a819-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a819-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a819-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="2a819-106">中正在加载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="2a819-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a819-107">备注</span><span class="sxs-lookup"><span data-stu-id="2a819-107">Remarks</span></span>  
 <span data-ttu-id="2a819-108">在调用[ICorProfilerCallback：： ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)方法之前，`moduleId` 的值对信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="2a819-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a819-109">需求</span><span class="sxs-lookup"><span data-stu-id="2a819-109">Requirements</span></span>  
 <span data-ttu-id="2a819-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a819-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a819-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a819-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a819-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a819-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a819-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a819-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a819-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a819-114">See also</span></span>

- [<span data-ttu-id="2a819-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2a819-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
