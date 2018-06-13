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
ms.openlocfilehash: cd53d74dfe8199617df47e46641b71203abf6e5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452343"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="a30d4-102">ICorProfilerCallback::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="a30d4-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="a30d4-103">调用以初始化代码探查器，每次启动新的公共语言运行时 (CLR) 应用程序时。</span><span class="sxs-lookup"><span data-stu-id="a30d4-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a30d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="a30d4-104">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a30d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="a30d4-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="a30d4-106">[在](/cpp/atl/iunknown)探查器必须查询的接口[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)接口指针。</span><span class="sxs-lookup"><span data-stu-id="a30d4-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a30d4-107">备注</span><span class="sxs-lookup"><span data-stu-id="a30d4-107">Remarks</span></span>  
 <span data-ttu-id="a30d4-108">`Initialize`调用是启用 （或禁用） 是不可变的回调的唯一机会。</span><span class="sxs-lookup"><span data-stu-id="a30d4-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="a30d4-109">通过启用回调后`Initialize`调用，则不能禁用更高版本使用[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a30d4-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="a30d4-110">COR_PRF_MONITOR_IMMUTABLE 值[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举指示哪些事件是不可变。</span><span class="sxs-lookup"><span data-stu-id="a30d4-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a30d4-111">要求</span><span class="sxs-lookup"><span data-stu-id="a30d4-111">Requirements</span></span>  
 <span data-ttu-id="a30d4-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a30d4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a30d4-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a30d4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a30d4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a30d4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a30d4-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a30d4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a30d4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a30d4-116">See Also</span></span>  
 [<span data-ttu-id="a30d4-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a30d4-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a30d4-118">Shutdown 方法</span><span class="sxs-lookup"><span data-stu-id="a30d4-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
