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
ms.openlocfilehash: 31dfd4654f849d01958be2690afed0f31c736dfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="f283a-102">ICLRPolicyManager::SetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="f283a-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="f283a-103">设置指定的操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="f283a-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f283a-104">语法</span><span class="sxs-lookup"><span data-stu-id="f283a-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f283a-105">参数</span><span class="sxs-lookup"><span data-stu-id="f283a-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="f283a-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，该值指示公共语言运行时 (CLR) 操作，为其设置超时。</span><span class="sxs-lookup"><span data-stu-id="f283a-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="f283a-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="f283a-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="f283a-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="f283a-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="f283a-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="f283a-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="f283a-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f283a-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="f283a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f283a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="f283a-112">[in]新超时值，以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="f283a-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="f283a-113">无限值会导致永远不会对超时的操作。</span><span class="sxs-lookup"><span data-stu-id="f283a-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f283a-114">返回值</span><span class="sxs-lookup"><span data-stu-id="f283a-114">Return Value</span></span>  
  
|<span data-ttu-id="f283a-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f283a-115">HRESULT</span></span>|<span data-ttu-id="f283a-116">描述</span><span class="sxs-lookup"><span data-stu-id="f283a-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f283a-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="f283a-117">S_OK</span></span>|<span data-ttu-id="f283a-118">`SetTimeout`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f283a-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="f283a-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f283a-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f283a-120">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f283a-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f283a-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f283a-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f283a-122">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="f283a-122">The call timed out.</span></span>|  
|<span data-ttu-id="f283a-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f283a-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f283a-124">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f283a-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f283a-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f283a-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f283a-126">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f283a-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f283a-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f283a-127">E_FAIL</span></span>|<span data-ttu-id="f283a-128">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f283a-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f283a-129">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="f283a-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f283a-130">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f283a-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f283a-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f283a-131">E_INVALIDARG</span></span>|<span data-ttu-id="f283a-132">超时不能设置为指定`operation`，或为提供的无效值`operation`。</span><span class="sxs-lookup"><span data-stu-id="f283a-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f283a-133">要求</span><span class="sxs-lookup"><span data-stu-id="f283a-133">Requirements</span></span>  
 <span data-ttu-id="f283a-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f283a-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f283a-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f283a-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f283a-136">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f283a-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f283a-137">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f283a-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f283a-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f283a-138">See Also</span></span>  
 [<span data-ttu-id="f283a-139">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="f283a-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="f283a-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="f283a-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="f283a-141">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="f283a-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
