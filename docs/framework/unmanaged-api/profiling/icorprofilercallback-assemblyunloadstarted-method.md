---
title: ICorProfilerCallback::AssemblyUnloadStarted 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c95bed520e0a4687541f127c8b39ef7916ef104
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122923"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="e43a3-102">ICorProfilerCallback::AssemblyUnloadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="e43a3-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="e43a3-103">通知探查器正在卸载程序集。</span><span class="sxs-lookup"><span data-stu-id="e43a3-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43a3-104">语法</span><span class="sxs-lookup"><span data-stu-id="e43a3-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e43a3-105">参数</span><span class="sxs-lookup"><span data-stu-id="e43a3-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="e43a3-106">[in]标识正在卸载的程序集。</span><span class="sxs-lookup"><span data-stu-id="e43a3-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e43a3-107">备注</span><span class="sxs-lookup"><span data-stu-id="e43a3-107">Remarks</span></span>  
 <span data-ttu-id="e43a3-108">值`assemblyId`不是有效的信息请求后`AssemblyUnloadStarted`方法将返回-这是探查器的最后一次机会来获取有关此程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="e43a3-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e43a3-109">要求</span><span class="sxs-lookup"><span data-stu-id="e43a3-109">Requirements</span></span>  
 <span data-ttu-id="e43a3-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e43a3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e43a3-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e43a3-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e43a3-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e43a3-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e43a3-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="e43a3-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e43a3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e43a3-114">See also</span></span>

- [<span data-ttu-id="e43a3-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e43a3-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e43a3-116">AssemblyUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="e43a3-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
