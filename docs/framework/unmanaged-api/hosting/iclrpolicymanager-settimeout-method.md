---
title: ICLRPolicyManager::SetTimeout 方法
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b16cc6a899b1ad5c814c29a93c6125250ca8186d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133570"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="a884c-102">ICLRPolicyManager::SetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="a884c-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="a884c-103">设置指定的操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="a884c-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a884c-104">语法</span><span class="sxs-lookup"><span data-stu-id="a884c-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a884c-105">参数</span><span class="sxs-lookup"><span data-stu-id="a884c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="a884c-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，它指示要为其设置超时值的公共语言运行时 (CLR) 操作。</span><span class="sxs-lookup"><span data-stu-id="a884c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="a884c-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="a884c-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="a884c-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="a884c-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="a884c-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="a884c-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="a884c-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a884c-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="a884c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a884c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="a884c-112">[in]新的超时值，以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="a884c-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="a884c-113">无限的值将导致操作永远不会超时。</span><span class="sxs-lookup"><span data-stu-id="a884c-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a884c-114">返回值</span><span class="sxs-lookup"><span data-stu-id="a884c-114">Return Value</span></span>  
  
|<span data-ttu-id="a884c-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a884c-115">HRESULT</span></span>|<span data-ttu-id="a884c-116">描述</span><span class="sxs-lookup"><span data-stu-id="a884c-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a884c-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="a884c-117">S_OK</span></span>|`SetTimeout` <span data-ttu-id="a884c-118">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a884c-118">returned successfully.</span></span>|  
|<span data-ttu-id="a884c-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a884c-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a884c-120">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a884c-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a884c-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a884c-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a884c-122">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="a884c-122">The call timed out.</span></span>|  
|<span data-ttu-id="a884c-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a884c-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a884c-124">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a884c-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a884c-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a884c-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a884c-126">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="a884c-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a884c-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a884c-127">E_FAIL</span></span>|<span data-ttu-id="a884c-128">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a884c-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a884c-129">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="a884c-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a884c-130">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a884c-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a884c-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a884c-131">E_INVALIDARG</span></span>|<span data-ttu-id="a884c-132">超时值不能设置为指定`operation`，或对于提供的值无效`operation`。</span><span class="sxs-lookup"><span data-stu-id="a884c-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a884c-133">要求</span><span class="sxs-lookup"><span data-stu-id="a884c-133">Requirements</span></span>  
 <span data-ttu-id="a884c-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a884c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a884c-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a884c-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a884c-136">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a884c-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a884c-137">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a884c-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a884c-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="a884c-138">See also</span></span>

- [<span data-ttu-id="a884c-139">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="a884c-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="a884c-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="a884c-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a884c-141">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="a884c-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
