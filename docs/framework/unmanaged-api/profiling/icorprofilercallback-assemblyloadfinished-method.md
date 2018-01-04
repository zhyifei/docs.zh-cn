---
title: "ICorProfilerCallback::AssemblyLoadFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9de280a1b92bc921ecb400c80522f21cf65f861a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="df02e-102">ICorProfilerCallback::AssemblyLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="df02e-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="df02e-103">通知探查器程序集已完成加载。</span><span class="sxs-lookup"><span data-stu-id="df02e-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df02e-104">语法</span><span class="sxs-lookup"><span data-stu-id="df02e-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df02e-105">参数</span><span class="sxs-lookup"><span data-stu-id="df02e-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="df02e-106">[in]标识已加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="df02e-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="df02e-107">[in]指示是否已完成的程序集，加载成功的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="df02e-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df02e-108">备注</span><span class="sxs-lookup"><span data-stu-id="df02e-108">Remarks</span></span>  
 <span data-ttu-id="df02e-109">值`assemblyId`无效的信息请求之前，不能`AssemblyLoadFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="df02e-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="df02e-110">加载程序集的某些部分可能会继续之后`AssemblyLoadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="df02e-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="df02e-111">失败的 HRESULT 在`hrStatus`指示失败。</span><span class="sxs-lookup"><span data-stu-id="df02e-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="df02e-112">但是，HRESULT 为成功，在`hrStatus`仅指示已成功加载程序集的第一部分。</span><span class="sxs-lookup"><span data-stu-id="df02e-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df02e-113">惠?</span><span class="sxs-lookup"><span data-stu-id="df02e-113">Requirements</span></span>  
 <span data-ttu-id="df02e-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df02e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df02e-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="df02e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="df02e-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df02e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df02e-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df02e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df02e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="df02e-118">See Also</span></span>  
 [<span data-ttu-id="df02e-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="df02e-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
