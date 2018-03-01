---
title: "ICorProfilerCallback::AssemblyUnloadStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9984cff1d3c4013d66bc9eb7dbe5dbe7b61d2ba3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="9602b-102">ICorProfilerCallback::AssemblyUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="9602b-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="9602b-103">通知探查器正在卸载程序集。</span><span class="sxs-lookup"><span data-stu-id="9602b-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9602b-104">语法</span><span class="sxs-lookup"><span data-stu-id="9602b-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9602b-105">参数</span><span class="sxs-lookup"><span data-stu-id="9602b-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="9602b-106">[in]标识正在卸载的程序集。</span><span class="sxs-lookup"><span data-stu-id="9602b-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9602b-107">备注</span><span class="sxs-lookup"><span data-stu-id="9602b-107">Remarks</span></span>  
 <span data-ttu-id="9602b-108">值`assemblyId`无效的信息请求后，不能`AssemblyUnloadStarted`方法返回-这是探查器的最后一次机会获取有关此程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="9602b-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9602b-109">惠?</span><span class="sxs-lookup"><span data-stu-id="9602b-109">Requirements</span></span>  
 <span data-ttu-id="9602b-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9602b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9602b-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9602b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9602b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9602b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9602b-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9602b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9602b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9602b-114">See Also</span></span>  
 [<span data-ttu-id="9602b-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9602b-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9602b-116">AssemblyUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="9602b-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
