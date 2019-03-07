---
title: ICorProfilerCallback::ModuleAttachedToAssembly 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6a8902df01e296c93bfbd94a1d90b0e3a40e81f0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480346"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="8e48f-102">ICorProfilerCallback::ModuleAttachedToAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="8e48f-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="8e48f-103">通知探查器模块，已附加到其父程序集。</span><span class="sxs-lookup"><span data-stu-id="8e48f-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e48f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e48f-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e48f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e48f-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="8e48f-106">[in]要附加的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="8e48f-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="8e48f-107">[in]该模块所附加到父程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="8e48f-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e48f-108">备注</span><span class="sxs-lookup"><span data-stu-id="8e48f-108">Remarks</span></span>  
 <span data-ttu-id="8e48f-109">可以通过调用通过导入地址表 (IAT) 加载的模块`LoadLibrary`，或通过元数据引用。</span><span class="sxs-lookup"><span data-stu-id="8e48f-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="8e48f-110">因此，公共语言运行时 (CLR) 加载程序具有多个代码路径用来确定在其中一个模块所在的程序集。</span><span class="sxs-lookup"><span data-stu-id="8e48f-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="8e48f-111">因此，很可能之后[icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)调用时，该模块不知道哪些程序集是中，且不可能获取父程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="8e48f-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="8e48f-112">`ModuleAttachedToAssembly`模块附加到其父程序集和它可以获取 ID 的父程序集时调用方法。</span><span class="sxs-lookup"><span data-stu-id="8e48f-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e48f-113">要求</span><span class="sxs-lookup"><span data-stu-id="8e48f-113">Requirements</span></span>  
 <span data-ttu-id="8e48f-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e48f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e48f-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e48f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e48f-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e48f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e48f-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e48f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e48f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e48f-118">See also</span></span>
- [<span data-ttu-id="8e48f-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="8e48f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
