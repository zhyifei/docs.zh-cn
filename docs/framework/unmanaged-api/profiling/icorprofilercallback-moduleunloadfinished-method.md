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
ms.openlocfilehash: f096c1f3898348141e13da44f39f2768417acd1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152238"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="70911-102">ICorProfilerCallback::ModuleUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="70911-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="70911-103">通知探查器模块已完成卸载。</span><span class="sxs-lookup"><span data-stu-id="70911-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70911-104">语法</span><span class="sxs-lookup"><span data-stu-id="70911-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70911-105">参数</span><span class="sxs-lookup"><span data-stu-id="70911-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="70911-106">[in]已卸载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="70911-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="70911-107">[in]一个 HRESULT，指示是否已成功将模块已被卸载。</span><span class="sxs-lookup"><span data-stu-id="70911-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70911-108">备注</span><span class="sxs-lookup"><span data-stu-id="70911-108">Remarks</span></span>  
 <span data-ttu-id="70911-109">值`moduleId`不是有效的信息请求后[icorprofilercallback:: Moduleunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="70911-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="70911-110">卸载类的某些部分可能会继续后`ModuleUnloadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="70911-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="70911-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="70911-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="70911-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功卸载该模块的第一部分。</span><span class="sxs-lookup"><span data-stu-id="70911-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70911-113">要求</span><span class="sxs-lookup"><span data-stu-id="70911-113">Requirements</span></span>  
 <span data-ttu-id="70911-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70911-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70911-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70911-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70911-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70911-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="70911-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="70911-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="70911-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="70911-118">See also</span></span>

- [<span data-ttu-id="70911-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="70911-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
