---
title: "ICorProfilerCallback::AssemblyUnloadFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ead41718e0253de599019112178d64c0ab706924
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="bb846-102">ICorProfilerCallback::AssemblyUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="bb846-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="bb846-103">通知探查器程序集已被卸载。</span><span class="sxs-lookup"><span data-stu-id="bb846-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb846-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb846-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb846-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb846-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="bb846-106">[in]标识正在卸载的程序集。</span><span class="sxs-lookup"><span data-stu-id="bb846-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bb846-107">[in]指示程序集是否已卸载成功的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="bb846-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb846-108">备注</span><span class="sxs-lookup"><span data-stu-id="bb846-108">Remarks</span></span>  
 <span data-ttu-id="bb846-109">值`assemblyId`无效的信息请求后，不能[icorprofilercallback:: Assemblyunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="bb846-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="bb846-110">卸载程序集的某些部分可能会继续之后`AssemblyUnloadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="bb846-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="bb846-111">失败的 HRESULT 在`hrStatus`指示失败。</span><span class="sxs-lookup"><span data-stu-id="bb846-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bb846-112">但是，HRESULT 为成功，在`hrStatus`仅指示已成功卸载程序集的第一部分。</span><span class="sxs-lookup"><span data-stu-id="bb846-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb846-113">惠?</span><span class="sxs-lookup"><span data-stu-id="bb846-113">Requirements</span></span>  
 <span data-ttu-id="bb846-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb846-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb846-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb846-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb846-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb846-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb846-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb846-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb846-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb846-118">See Also</span></span>  
 [<span data-ttu-id="bb846-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="bb846-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
