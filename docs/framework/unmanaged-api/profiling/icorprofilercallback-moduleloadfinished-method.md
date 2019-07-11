---
title: ICorProfilerCallback::ModuleLoadFinished 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c04b7862363b441ab35d6dd364c4dffaf7464153
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769226"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="eab19-102">ICorProfilerCallback::ModuleLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="eab19-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="eab19-103">通知探查器模块已完成加载。</span><span class="sxs-lookup"><span data-stu-id="eab19-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eab19-104">语法</span><span class="sxs-lookup"><span data-stu-id="eab19-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eab19-105">参数</span><span class="sxs-lookup"><span data-stu-id="eab19-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="eab19-106">[in]已完成加载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="eab19-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="eab19-107">[in]一个 HRESULT，指示是否已成功加载的模块。</span><span class="sxs-lookup"><span data-stu-id="eab19-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eab19-108">备注</span><span class="sxs-lookup"><span data-stu-id="eab19-108">Remarks</span></span>  
 <span data-ttu-id="eab19-109">值`moduleId`不是有效信息请求直到`ModuleLoadFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="eab19-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="eab19-110">加载该模块的某些部分可能会继续后`ModuleLoadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="eab19-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="eab19-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="eab19-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="eab19-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功加载该模块的第一部分。</span><span class="sxs-lookup"><span data-stu-id="eab19-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eab19-113">要求</span><span class="sxs-lookup"><span data-stu-id="eab19-113">Requirements</span></span>  
 <span data-ttu-id="eab19-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eab19-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eab19-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eab19-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eab19-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eab19-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eab19-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eab19-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eab19-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="eab19-118">See also</span></span>

- [<span data-ttu-id="eab19-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="eab19-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="eab19-120">ModuleLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="eab19-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
