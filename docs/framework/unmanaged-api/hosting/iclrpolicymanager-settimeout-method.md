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
ms.openlocfilehash: d9c2ebb2bc9c1137a4e3716d98387278959f77d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757317"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="84307-102">ICLRPolicyManager::SetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="84307-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="84307-103">设置指定的操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="84307-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84307-104">语法</span><span class="sxs-lookup"><span data-stu-id="84307-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84307-105">参数</span><span class="sxs-lookup"><span data-stu-id="84307-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="84307-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，它指示要为其设置超时值的公共语言运行时 (CLR) 操作。</span><span class="sxs-lookup"><span data-stu-id="84307-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="84307-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="84307-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="84307-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="84307-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="84307-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="84307-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="84307-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="84307-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="84307-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="84307-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="84307-112">[in]新的超时值，以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="84307-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="84307-113">无限的值将导致操作永远不会超时。</span><span class="sxs-lookup"><span data-stu-id="84307-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84307-114">返回值</span><span class="sxs-lookup"><span data-stu-id="84307-114">Return Value</span></span>  
  
|<span data-ttu-id="84307-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84307-115">HRESULT</span></span>|<span data-ttu-id="84307-116">描述</span><span class="sxs-lookup"><span data-stu-id="84307-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84307-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="84307-117">S_OK</span></span>|<span data-ttu-id="84307-118">`SetTimeout` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="84307-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="84307-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84307-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84307-120">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="84307-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84307-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84307-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84307-122">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="84307-122">The call timed out.</span></span>|  
|<span data-ttu-id="84307-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84307-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84307-124">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="84307-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84307-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84307-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84307-126">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="84307-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84307-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84307-127">E_FAIL</span></span>|<span data-ttu-id="84307-128">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="84307-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84307-129">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="84307-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84307-130">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="84307-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="84307-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="84307-131">E_INVALIDARG</span></span>|<span data-ttu-id="84307-132">超时值不能设置为指定`operation`，或对于提供的值无效`operation`。</span><span class="sxs-lookup"><span data-stu-id="84307-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84307-133">要求</span><span class="sxs-lookup"><span data-stu-id="84307-133">Requirements</span></span>  
 <span data-ttu-id="84307-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84307-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84307-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="84307-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84307-136">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="84307-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84307-137">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84307-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84307-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="84307-138">See also</span></span>

- [<span data-ttu-id="84307-139">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="84307-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="84307-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="84307-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="84307-141">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="84307-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
