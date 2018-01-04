---
title: "ICLRPolicyManager::SetTimeout 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetTimeout
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5042d2f06d25b2cccc81239367362313210d3c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="6a887-102">ICLRPolicyManager::SetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="6a887-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="6a887-103">设置指定的操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="6a887-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a887-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a887-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a887-105">参数</span><span class="sxs-lookup"><span data-stu-id="6a887-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="6a887-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，该值指示公共语言运行时 (CLR) 操作，为其设置超时。</span><span class="sxs-lookup"><span data-stu-id="6a887-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="6a887-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="6a887-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="6a887-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="6a887-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="6a887-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="6a887-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="6a887-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="6a887-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="6a887-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="6a887-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="6a887-112">[in]新超时值，以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="6a887-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="6a887-113">无限值会导致永远不会对超时的操作。</span><span class="sxs-lookup"><span data-stu-id="6a887-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a887-114">返回值</span><span class="sxs-lookup"><span data-stu-id="6a887-114">Return Value</span></span>  
  
|<span data-ttu-id="6a887-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a887-115">HRESULT</span></span>|<span data-ttu-id="6a887-116">描述</span><span class="sxs-lookup"><span data-stu-id="6a887-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6a887-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a887-117">S_OK</span></span>|<span data-ttu-id="6a887-118">`SetTimeout`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="6a887-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="6a887-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6a887-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6a887-120">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="6a887-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6a887-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6a887-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6a887-122">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="6a887-122">The call timed out.</span></span>|  
|<span data-ttu-id="6a887-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6a887-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6a887-124">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="6a887-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6a887-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6a887-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6a887-126">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="6a887-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6a887-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6a887-127">E_FAIL</span></span>|<span data-ttu-id="6a887-128">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="6a887-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6a887-129">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="6a887-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6a887-130">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="6a887-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6a887-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6a887-131">E_INVALIDARG</span></span>|<span data-ttu-id="6a887-132">超时不能设置为指定`operation`，或为提供的无效值`operation`。</span><span class="sxs-lookup"><span data-stu-id="6a887-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a887-133">惠?</span><span class="sxs-lookup"><span data-stu-id="6a887-133">Requirements</span></span>  
 <span data-ttu-id="6a887-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a887-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a887-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a887-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a887-136">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6a887-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a887-137">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a887-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a887-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a887-138">See Also</span></span>  
 [<span data-ttu-id="6a887-139">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="6a887-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="6a887-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="6a887-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="6a887-141">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="6a887-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
