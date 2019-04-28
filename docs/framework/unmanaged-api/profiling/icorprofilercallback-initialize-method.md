---
title: ICorProfilerCallback::Initialize 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16001c4af2bcd8aa8d5fff6b06fa8c275bc24cb9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597473"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="36d72-102">ICorProfilerCallback::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="36d72-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="36d72-103">调用以初始化代码探查器每次启动新的公共语言运行时 (CLR) 应用程序时。</span><span class="sxs-lookup"><span data-stu-id="36d72-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d72-104">语法</span><span class="sxs-lookup"><span data-stu-id="36d72-104">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36d72-105">参数</span><span class="sxs-lookup"><span data-stu-id="36d72-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="36d72-106">[在中](/cpp/atl/iunknown)探查器必须查询接口[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)接口指针。</span><span class="sxs-lookup"><span data-stu-id="36d72-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36d72-107">备注</span><span class="sxs-lookup"><span data-stu-id="36d72-107">Remarks</span></span>  
 <span data-ttu-id="36d72-108">`Initialize`调用是启用 （或禁用） 是固定不变的回调的唯一机会。</span><span class="sxs-lookup"><span data-stu-id="36d72-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="36d72-109">通过启用回调后`Initialize`调用，不能禁用更高版本使用[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)。</span><span class="sxs-lookup"><span data-stu-id="36d72-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="36d72-110">值 COR_PRF_MONITOR_IMMUTABLE [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举指示哪个事件是固定不变。</span><span class="sxs-lookup"><span data-stu-id="36d72-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36d72-111">要求</span><span class="sxs-lookup"><span data-stu-id="36d72-111">Requirements</span></span>  
 <span data-ttu-id="36d72-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36d72-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36d72-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36d72-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36d72-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36d72-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36d72-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36d72-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d72-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="36d72-116">See also</span></span>

- [<span data-ttu-id="36d72-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="36d72-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="36d72-118">Shutdown 方法</span><span class="sxs-lookup"><span data-stu-id="36d72-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
