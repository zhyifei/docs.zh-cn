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
ms.openlocfilehash: 0851ac33a2bac4fcf727cf09e5225f6b83481b50
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866669"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="ba1ea-102">ICorProfilerCallback::AppDomainShutdownFinished 方法</span><span class="sxs-lookup"><span data-stu-id="ba1ea-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="ba1ea-103">通知探查器已从进程中卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="ba1ea-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba1ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba1ea-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba1ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba1ea-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="ba1ea-106">\[中的] 标识存储应用程序的程序集的域。</span><span class="sxs-lookup"><span data-stu-id="ba1ea-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="ba1ea-107">\[中的] HRESULT，它指示是否已成功卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="ba1ea-107">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba1ea-108">备注</span><span class="sxs-lookup"><span data-stu-id="ba1ea-108">Remarks</span></span>  
 <span data-ttu-id="ba1ea-109">[ICorProfilerCallback：： AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md)方法返回后，`appDomainId` 的值对信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="ba1ea-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="ba1ea-110">在 `AppDomainCreationFinished` 回调后，卸载应用程序域的某些部分可能会继续。</span><span class="sxs-lookup"><span data-stu-id="ba1ea-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="ba1ea-111">如果 `hrStatus` 失败，则指示失败。</span><span class="sxs-lookup"><span data-stu-id="ba1ea-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="ba1ea-112">不过，`hrStatus` 中的 HRESULT 成功仅指示卸载应用程序域的第一部分已成功。</span><span class="sxs-lookup"><span data-stu-id="ba1ea-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba1ea-113">需求</span><span class="sxs-lookup"><span data-stu-id="ba1ea-113">Requirements</span></span>  
 <span data-ttu-id="ba1ea-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba1ea-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba1ea-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ba1ea-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ba1ea-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba1ea-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba1ea-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba1ea-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba1ea-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba1ea-118">See also</span></span>

- [<span data-ttu-id="ba1ea-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ba1ea-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
