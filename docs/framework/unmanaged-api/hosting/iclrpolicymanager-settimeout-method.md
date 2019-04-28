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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638835"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="6c650-102">ICLRPolicyManager::SetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="6c650-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="6c650-103">设置指定的操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="6c650-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c650-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c650-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c650-105">参数</span><span class="sxs-lookup"><span data-stu-id="6c650-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="6c650-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，它指示要为其设置超时值的公共语言运行时 (CLR) 操作。</span><span class="sxs-lookup"><span data-stu-id="6c650-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="6c650-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="6c650-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="6c650-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="6c650-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="6c650-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="6c650-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="6c650-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="6c650-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="6c650-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="6c650-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="6c650-112">[in]新的超时值，以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="6c650-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="6c650-113">无限的值将导致操作永远不会超时。</span><span class="sxs-lookup"><span data-stu-id="6c650-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c650-114">返回值</span><span class="sxs-lookup"><span data-stu-id="6c650-114">Return Value</span></span>  
  
|<span data-ttu-id="6c650-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c650-115">HRESULT</span></span>|<span data-ttu-id="6c650-116">描述</span><span class="sxs-lookup"><span data-stu-id="6c650-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c650-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c650-117">S_OK</span></span>|<span data-ttu-id="6c650-118">`SetTimeout` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="6c650-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="6c650-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6c650-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6c650-120">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="6c650-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6c650-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6c650-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6c650-122">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="6c650-122">The call timed out.</span></span>|  
|<span data-ttu-id="6c650-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6c650-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6c650-124">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="6c650-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6c650-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6c650-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6c650-126">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="6c650-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6c650-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6c650-127">E_FAIL</span></span>|<span data-ttu-id="6c650-128">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="6c650-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6c650-129">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="6c650-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6c650-130">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="6c650-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6c650-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6c650-131">E_INVALIDARG</span></span>|<span data-ttu-id="6c650-132">超时值不能设置为指定`operation`，或对于提供的值无效`operation`。</span><span class="sxs-lookup"><span data-stu-id="6c650-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c650-133">要求</span><span class="sxs-lookup"><span data-stu-id="6c650-133">Requirements</span></span>  
 <span data-ttu-id="6c650-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6c650-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c650-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c650-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c650-136">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6c650-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c650-137">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c650-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c650-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c650-138">See also</span></span>

- [<span data-ttu-id="6c650-139">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="6c650-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="6c650-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="6c650-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6c650-141">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="6c650-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
