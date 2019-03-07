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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16973fe322a0fbd7a2433cd94982df04eb13dc50
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468723"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="3b4e7-102">ICorProfilerCallback::AppDomainShutdownFinished 方法</span><span class="sxs-lookup"><span data-stu-id="3b4e7-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="3b4e7-103">通知探查器已从进程中卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="3b4e7-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b4e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b4e7-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b4e7-105">参数</span><span class="sxs-lookup"><span data-stu-id="3b4e7-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="3b4e7-106">[in]标识应用程序的程序集存储在其中的域。</span><span class="sxs-lookup"><span data-stu-id="3b4e7-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="3b4e7-107">[in]一个 HRESULT，指示是否已成功应用程序域已被卸载。</span><span class="sxs-lookup"><span data-stu-id="3b4e7-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b4e7-108">备注</span><span class="sxs-lookup"><span data-stu-id="3b4e7-108">Remarks</span></span>  
 <span data-ttu-id="3b4e7-109">值`appDomainId`不是有效的信息请求后[icorprofilercallback:: Appdomainshutdownstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="3b4e7-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="3b4e7-110">卸载应用程序域的某些部分可能会继续后`AppDomainCreationFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="3b4e7-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="3b4e7-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="3b4e7-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="3b4e7-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功卸载应用程序域的第一部分。</span><span class="sxs-lookup"><span data-stu-id="3b4e7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b4e7-113">要求</span><span class="sxs-lookup"><span data-stu-id="3b4e7-113">Requirements</span></span>  
 <span data-ttu-id="3b4e7-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b4e7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b4e7-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b4e7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b4e7-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b4e7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b4e7-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b4e7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4e7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b4e7-118">See also</span></span>
- [<span data-ttu-id="3b4e7-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3b4e7-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
