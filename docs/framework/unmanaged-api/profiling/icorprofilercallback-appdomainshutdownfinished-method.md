---
title: ICorProfilerCallback::AppDomainShutdownFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
ms.openlocfilehash: 8ff7d5a593388bd3a584e031aea411dfdb6c9845
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445196"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="e42ef-102">ICorProfilerCallback::AppDomainShutdownFinished 方法</span><span class="sxs-lookup"><span data-stu-id="e42ef-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="e42ef-103">Notifies the profiler that an application domain has been unloaded from a process.</span><span class="sxs-lookup"><span data-stu-id="e42ef-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e42ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="e42ef-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e42ef-105">参数</span><span class="sxs-lookup"><span data-stu-id="e42ef-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="e42ef-106">[in] Identifies the domain in which the application's assemblies are stored.</span><span class="sxs-lookup"><span data-stu-id="e42ef-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="e42ef-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span><span class="sxs-lookup"><span data-stu-id="e42ef-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e42ef-108">备注</span><span class="sxs-lookup"><span data-stu-id="e42ef-108">Remarks</span></span>  
 <span data-ttu-id="e42ef-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span><span class="sxs-lookup"><span data-stu-id="e42ef-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="e42ef-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="e42ef-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="e42ef-111">A failure HRESULT in `hrStatus` indicates a failure.</span><span class="sxs-lookup"><span data-stu-id="e42ef-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e42ef-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span><span class="sxs-lookup"><span data-stu-id="e42ef-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e42ef-113">要求</span><span class="sxs-lookup"><span data-stu-id="e42ef-113">Requirements</span></span>  
 <span data-ttu-id="e42ef-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e42ef-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e42ef-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e42ef-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e42ef-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e42ef-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e42ef-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e42ef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e42ef-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e42ef-118">See also</span></span>

- [<span data-ttu-id="e42ef-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e42ef-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
