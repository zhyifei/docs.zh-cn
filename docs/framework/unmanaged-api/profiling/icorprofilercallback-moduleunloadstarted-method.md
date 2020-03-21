---
title: ICorProfilerCallback::ModuleUnloadStarted 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: fcfdddbd5316c098754ea7b0d4714b050c64fe55
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175143"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="21a39-102">ICorProfilerCallback::ModuleUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="21a39-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="21a39-103">通知探查器正在卸载模块。</span><span class="sxs-lookup"><span data-stu-id="21a39-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a39-104">语法</span><span class="sxs-lookup"><span data-stu-id="21a39-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="21a39-105">parameters</span><span class="sxs-lookup"><span data-stu-id="21a39-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="21a39-106">[在]正在卸载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="21a39-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21a39-107">备注</span><span class="sxs-lookup"><span data-stu-id="21a39-107">Remarks</span></span>  
 <span data-ttu-id="21a39-108">返回`ModuleUnloadStarted`后，`moduleId`值对信息请求无效 - 这是探查器获取有关此模块信息的最后机会。</span><span class="sxs-lookup"><span data-stu-id="21a39-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21a39-109">要求</span><span class="sxs-lookup"><span data-stu-id="21a39-109">Requirements</span></span>  
 <span data-ttu-id="21a39-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21a39-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21a39-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21a39-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21a39-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21a39-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21a39-113">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21a39-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a39-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21a39-114">See also</span></span>

- [<span data-ttu-id="21a39-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="21a39-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="21a39-116">ModuleUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="21a39-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
