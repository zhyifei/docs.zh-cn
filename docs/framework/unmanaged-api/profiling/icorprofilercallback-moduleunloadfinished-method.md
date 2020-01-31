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
ms.openlocfilehash: b13573d19ab4d8bb655c1e153530dc70173abe82
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866138"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="6f5e9-102">ICorProfilerCallback::ModuleUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="6f5e9-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="6f5e9-103">通知探查器模块已完成卸载。</span><span class="sxs-lookup"><span data-stu-id="6f5e9-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f5e9-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f5e9-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f5e9-105">参数</span><span class="sxs-lookup"><span data-stu-id="6f5e9-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="6f5e9-106">中已卸载的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="6f5e9-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="6f5e9-107">中一个 HRESULT，指示该模块是否已成功卸载。</span><span class="sxs-lookup"><span data-stu-id="6f5e9-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f5e9-108">备注</span><span class="sxs-lookup"><span data-stu-id="6f5e9-108">Remarks</span></span>  
 <span data-ttu-id="6f5e9-109">[ICorProfilerCallback：： ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md)方法返回后，`moduleId` 的值对信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="6f5e9-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="6f5e9-110">在 `ModuleUnloadFinished` 回调后，卸载类的某些部分可能会继续。</span><span class="sxs-lookup"><span data-stu-id="6f5e9-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="6f5e9-111">如果 `hrStatus` 失败，则指示失败。</span><span class="sxs-lookup"><span data-stu-id="6f5e9-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="6f5e9-112">不过，`hrStatus` 中的 HRESULT 成功只指示卸载模块的第一部分已成功。</span><span class="sxs-lookup"><span data-stu-id="6f5e9-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f5e9-113">需求</span><span class="sxs-lookup"><span data-stu-id="6f5e9-113">Requirements</span></span>  
 <span data-ttu-id="6f5e9-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6f5e9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f5e9-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f5e9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f5e9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f5e9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f5e9-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f5e9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5e9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f5e9-118">See also</span></span>

- [<span data-ttu-id="6f5e9-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6f5e9-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
