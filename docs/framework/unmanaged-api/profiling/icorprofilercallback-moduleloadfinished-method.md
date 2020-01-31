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
ms.openlocfilehash: 661229e5fbd5d106662f0e823a1753bd76c33311
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866164"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="31ce7-102">ICorProfilerCallback::ModuleLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="31ce7-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="31ce7-103">通知探查器模块已完成加载。</span><span class="sxs-lookup"><span data-stu-id="31ce7-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31ce7-104">语法</span><span class="sxs-lookup"><span data-stu-id="31ce7-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31ce7-105">参数</span><span class="sxs-lookup"><span data-stu-id="31ce7-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="31ce7-106">中已完成加载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="31ce7-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="31ce7-107">中一个 HRESULT，指示是否已成功加载该模块。</span><span class="sxs-lookup"><span data-stu-id="31ce7-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31ce7-108">备注</span><span class="sxs-lookup"><span data-stu-id="31ce7-108">Remarks</span></span>  
 <span data-ttu-id="31ce7-109">在调用 `ModuleLoadFinished` 方法之前，`moduleId` 的值对信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="31ce7-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="31ce7-110">在 `ModuleLoadFinished` 回调后，加载模块的某些部分可能会继续。</span><span class="sxs-lookup"><span data-stu-id="31ce7-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="31ce7-111">如果 `hrStatus` 失败，则指示失败。</span><span class="sxs-lookup"><span data-stu-id="31ce7-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="31ce7-112">不过，`hrStatus` 中的 HRESULT 成功只指示加载模块的第一部分已成功完成。</span><span class="sxs-lookup"><span data-stu-id="31ce7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31ce7-113">需求</span><span class="sxs-lookup"><span data-stu-id="31ce7-113">Requirements</span></span>  
 <span data-ttu-id="31ce7-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31ce7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31ce7-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31ce7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31ce7-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31ce7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31ce7-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31ce7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ce7-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31ce7-118">See also</span></span>

- [<span data-ttu-id="31ce7-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="31ce7-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="31ce7-120">ModuleLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="31ce7-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
