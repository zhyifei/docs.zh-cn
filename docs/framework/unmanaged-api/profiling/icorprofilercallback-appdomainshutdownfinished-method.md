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
ms.openlocfilehash: 3f9f8925630933e2247726f92a93cac67bdc55ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450484"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="4cdb9-102">ICorProfilerCallback::AppDomainShutdownFinished 方法</span><span class="sxs-lookup"><span data-stu-id="4cdb9-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="4cdb9-103">通知探查器已从进程中卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="4cdb9-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cdb9-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cdb9-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cdb9-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cdb9-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="4cdb9-106">[in]标识应用程序的程序集存储在其中的域。</span><span class="sxs-lookup"><span data-stu-id="4cdb9-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="4cdb9-107">[in]一个 HRESULT，指示是否已成功应用程序域已被卸载。</span><span class="sxs-lookup"><span data-stu-id="4cdb9-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cdb9-108">备注</span><span class="sxs-lookup"><span data-stu-id="4cdb9-108">Remarks</span></span>  
 <span data-ttu-id="4cdb9-109">值`appDomainId`无效的信息请求后，不能[icorprofilercallback:: Appdomainshutdownstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="4cdb9-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="4cdb9-110">卸载应用程序域的某些部分可能会继续之后`AppDomainCreationFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="4cdb9-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="4cdb9-111">失败的 HRESULT 在`hrStatus`指示失败。</span><span class="sxs-lookup"><span data-stu-id="4cdb9-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="4cdb9-112">但是，HRESULT 为成功，在`hrStatus`仅指示已成功卸载应用程序域的第一部分。</span><span class="sxs-lookup"><span data-stu-id="4cdb9-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cdb9-113">要求</span><span class="sxs-lookup"><span data-stu-id="4cdb9-113">Requirements</span></span>  
 <span data-ttu-id="4cdb9-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cdb9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cdb9-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4cdb9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4cdb9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cdb9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cdb9-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cdb9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cdb9-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cdb9-118">See Also</span></span>  
 [<span data-ttu-id="4cdb9-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4cdb9-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
