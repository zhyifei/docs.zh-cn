---
title: ICorProfilerCallback::ModuleUnloadFinished 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6462fe44459228a377f4e583a8a5a1cd93d939bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480359"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="09630-102">ICorProfilerCallback::ModuleUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="09630-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="09630-103">通知探查器模块已完成卸载。</span><span class="sxs-lookup"><span data-stu-id="09630-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09630-104">语法</span><span class="sxs-lookup"><span data-stu-id="09630-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09630-105">参数</span><span class="sxs-lookup"><span data-stu-id="09630-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="09630-106">[in]已卸载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="09630-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="09630-107">[in]一个 HRESULT，指示是否已成功将模块已被卸载。</span><span class="sxs-lookup"><span data-stu-id="09630-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09630-108">备注</span><span class="sxs-lookup"><span data-stu-id="09630-108">Remarks</span></span>  
 <span data-ttu-id="09630-109">值`moduleId`不是有效的信息请求后[icorprofilercallback:: Moduleunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="09630-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="09630-110">卸载类的某些部分可能会继续后`ModuleUnloadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="09630-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="09630-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="09630-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="09630-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功卸载该模块的第一部分。</span><span class="sxs-lookup"><span data-stu-id="09630-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09630-113">要求</span><span class="sxs-lookup"><span data-stu-id="09630-113">Requirements</span></span>  
 <span data-ttu-id="09630-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09630-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09630-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09630-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09630-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09630-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09630-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09630-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09630-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="09630-118">See also</span></span>
- [<span data-ttu-id="09630-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="09630-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
