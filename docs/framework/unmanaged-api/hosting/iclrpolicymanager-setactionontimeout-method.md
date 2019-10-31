---
title: ICLRPolicyManager::SetActionOnTimeout 方法
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
ms.openlocfilehash: 9ef906ed5e8a6985c084741bf06b683da79c546e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140791"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="64e5d-102">ICLRPolicyManager::SetActionOnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="64e5d-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="64e5d-103">指定在指定操作超时时公共语言运行时（CLR）应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="64e5d-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64e5d-104">语法</span><span class="sxs-lookup"><span data-stu-id="64e5d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64e5d-105">参数</span><span class="sxs-lookup"><span data-stu-id="64e5d-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="64e5d-106">中[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值之一，指示要为其指定超时操作的操作。</span><span class="sxs-lookup"><span data-stu-id="64e5d-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="64e5d-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="64e5d-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="64e5d-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="64e5d-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="64e5d-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="64e5d-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="64e5d-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="64e5d-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="64e5d-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="64e5d-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="64e5d-112">中[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值之一，指示操作超时时要执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="64e5d-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64e5d-113">返回值</span><span class="sxs-lookup"><span data-stu-id="64e5d-113">Return Value</span></span>  
  
|<span data-ttu-id="64e5d-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64e5d-114">HRESULT</span></span>|<span data-ttu-id="64e5d-115">描述</span><span class="sxs-lookup"><span data-stu-id="64e5d-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64e5d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="64e5d-116">S_OK</span></span>|<span data-ttu-id="64e5d-117">`SetActionOnTimeout` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="64e5d-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="64e5d-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64e5d-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="64e5d-119">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="64e5d-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="64e5d-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64e5d-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="64e5d-121">调用超时。</span><span class="sxs-lookup"><span data-stu-id="64e5d-121">The call timed out.</span></span>|  
|<span data-ttu-id="64e5d-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="64e5d-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="64e5d-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="64e5d-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="64e5d-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="64e5d-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="64e5d-125">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="64e5d-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="64e5d-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64e5d-126">E_FAIL</span></span>|<span data-ttu-id="64e5d-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="64e5d-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64e5d-128">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="64e5d-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="64e5d-129">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="64e5d-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="64e5d-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="64e5d-130">E_INVALIDARG</span></span>|<span data-ttu-id="64e5d-131">无法为指定的 `operation`设置超时，或为 `operation`提供的值无效。</span><span class="sxs-lookup"><span data-stu-id="64e5d-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64e5d-132">备注</span><span class="sxs-lookup"><span data-stu-id="64e5d-132">Remarks</span></span>  
 <span data-ttu-id="64e5d-133">超时值可以是 CLR 设置的默认超时值，也可以是主机在[ICLRPolicyManager：： SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)方法的调用中指定的值。</span><span class="sxs-lookup"><span data-stu-id="64e5d-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="64e5d-134">并非所有策略操作值都可以指定为 CLR 操作的超时行为。</span><span class="sxs-lookup"><span data-stu-id="64e5d-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="64e5d-135">`SetActionOnTimeout` 通常仅用于升级行为。</span><span class="sxs-lookup"><span data-stu-id="64e5d-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="64e5d-136">例如，主机可以指定线程中止进入强制线程中止，但不能指定相反的。</span><span class="sxs-lookup"><span data-stu-id="64e5d-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="64e5d-137">下表描述了有效 `operation` 值的有效 `action` 值。</span><span class="sxs-lookup"><span data-stu-id="64e5d-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="64e5d-138">`operation` 的值</span><span class="sxs-lookup"><span data-stu-id="64e5d-138">Value for `operation`</span></span>|<span data-ttu-id="64e5d-139">`action` 的有效值</span><span class="sxs-lookup"><span data-stu-id="64e5d-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="64e5d-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="64e5d-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="64e5d-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="64e5d-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="64e5d-142">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="64e5d-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="64e5d-143">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="64e5d-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="64e5d-144">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="64e5d-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="64e5d-145">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="64e5d-145">-   eExitProcess</span></span><br /><span data-ttu-id="64e5d-146">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="64e5d-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="64e5d-147">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="64e5d-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="64e5d-148">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="64e5d-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="64e5d-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="64e5d-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="64e5d-150">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="64e5d-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="64e5d-151">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="64e5d-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="64e5d-152">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="64e5d-152">-   eExitProcess</span></span><br /><span data-ttu-id="64e5d-153">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="64e5d-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="64e5d-154">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="64e5d-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="64e5d-155">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="64e5d-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="64e5d-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="64e5d-156">OPR_ProcessExit</span></span>|<span data-ttu-id="64e5d-157">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="64e5d-157">-   eExitProcess</span></span><br /><span data-ttu-id="64e5d-158">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="64e5d-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="64e5d-159">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="64e5d-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="64e5d-160">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="64e5d-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64e5d-161">要求</span><span class="sxs-lookup"><span data-stu-id="64e5d-161">Requirements</span></span>  
 <span data-ttu-id="64e5d-162">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64e5d-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64e5d-163">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="64e5d-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64e5d-164">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="64e5d-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64e5d-165">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64e5d-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e5d-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="64e5d-166">See also</span></span>

- [<span data-ttu-id="64e5d-167">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="64e5d-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="64e5d-168">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="64e5d-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="64e5d-169">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="64e5d-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="64e5d-170">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="64e5d-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
