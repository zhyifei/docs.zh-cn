---
title: ICorProfilerCallback::AssemblyUnloadFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9ee87c926d2377ff8eef53f930fe75251b28ceb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597867"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="55966-102">ICorProfilerCallback::AssemblyUnloadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="55966-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="55966-103">通知探查器程序集已被卸载。</span><span class="sxs-lookup"><span data-stu-id="55966-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55966-104">语法</span><span class="sxs-lookup"><span data-stu-id="55966-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55966-105">参数</span><span class="sxs-lookup"><span data-stu-id="55966-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="55966-106">[in]标识正在卸载的程序集。</span><span class="sxs-lookup"><span data-stu-id="55966-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="55966-107">[in]一个 HRESULT，指示是否已成功将程序集已被卸载。</span><span class="sxs-lookup"><span data-stu-id="55966-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55966-108">备注</span><span class="sxs-lookup"><span data-stu-id="55966-108">Remarks</span></span>  
 <span data-ttu-id="55966-109">值`assemblyId`不是有效的信息请求后[icorprofilercallback:: Assemblyunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="55966-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="55966-110">卸载该程序集的某些部分可能会继续后`AssemblyUnloadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="55966-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="55966-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="55966-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="55966-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功卸载该程序集的第一部分。</span><span class="sxs-lookup"><span data-stu-id="55966-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55966-113">要求</span><span class="sxs-lookup"><span data-stu-id="55966-113">Requirements</span></span>  
 <span data-ttu-id="55966-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55966-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55966-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55966-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55966-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55966-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55966-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55966-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55966-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="55966-118">See also</span></span>

- [<span data-ttu-id="55966-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="55966-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
