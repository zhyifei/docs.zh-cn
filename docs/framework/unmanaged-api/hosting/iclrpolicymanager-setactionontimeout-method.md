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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7844ca5aefad94542146dc5eba6a966143ff8327
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612848"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="ddd19-102">ICLRPolicyManager::SetActionOnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="ddd19-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="ddd19-103">指定公共语言运行时 (CLR) 应执行指定的操作超时时的策略操作。</span><span class="sxs-lookup"><span data-stu-id="ddd19-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddd19-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddd19-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddd19-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddd19-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="ddd19-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，它指示要为其指定的超时操作的操作。</span><span class="sxs-lookup"><span data-stu-id="ddd19-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="ddd19-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="ddd19-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="ddd19-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="ddd19-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="ddd19-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="ddd19-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="ddd19-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ddd19-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="ddd19-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ddd19-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="ddd19-112">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，它指示要执行该操作超时时策略操作。</span><span class="sxs-lookup"><span data-stu-id="ddd19-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddd19-113">返回值</span><span class="sxs-lookup"><span data-stu-id="ddd19-113">Return Value</span></span>  
  
|<span data-ttu-id="ddd19-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ddd19-114">HRESULT</span></span>|<span data-ttu-id="ddd19-115">描述</span><span class="sxs-lookup"><span data-stu-id="ddd19-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ddd19-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="ddd19-116">S_OK</span></span>|<span data-ttu-id="ddd19-117">`SetActionOnTimeout` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ddd19-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="ddd19-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ddd19-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ddd19-119">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ddd19-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ddd19-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ddd19-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ddd19-121">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="ddd19-121">The call timed out.</span></span>|  
|<span data-ttu-id="ddd19-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ddd19-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ddd19-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ddd19-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ddd19-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ddd19-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ddd19-125">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ddd19-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ddd19-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ddd19-126">E_FAIL</span></span>|<span data-ttu-id="ddd19-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ddd19-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ddd19-128">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="ddd19-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ddd19-129">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ddd19-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ddd19-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ddd19-130">E_INVALIDARG</span></span>|<span data-ttu-id="ddd19-131">超时值不能设置为指定`operation`，或对于提供的值无效`operation`。</span><span class="sxs-lookup"><span data-stu-id="ddd19-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddd19-132">备注</span><span class="sxs-lookup"><span data-stu-id="ddd19-132">Remarks</span></span>  
 <span data-ttu-id="ddd19-133">超时值可以是由 CLR，设置的默认超时或在调用 host 所指定的值[iclrpolicymanager:: Settimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ddd19-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="ddd19-134">并非所有策略操作值可以都指定为对于 CLR 操作的超时行为。</span><span class="sxs-lookup"><span data-stu-id="ddd19-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="ddd19-135">`SetActionOnTimeout` 通常仅用于提升行为。</span><span class="sxs-lookup"><span data-stu-id="ddd19-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="ddd19-136">例如，主机可以指定线程中止转变为强制线程终止，但不能指定相反。</span><span class="sxs-lookup"><span data-stu-id="ddd19-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="ddd19-137">下表列出了有效`action`值为有效`operation`值。</span><span class="sxs-lookup"><span data-stu-id="ddd19-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="ddd19-138">值 `operation`</span><span class="sxs-lookup"><span data-stu-id="ddd19-138">Value for `operation`</span></span>|<span data-ttu-id="ddd19-139">有效值 `action`</span><span class="sxs-lookup"><span data-stu-id="ddd19-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="ddd19-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ddd19-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="ddd19-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ddd19-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="ddd19-142">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="ddd19-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="ddd19-143">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddd19-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ddd19-144">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddd19-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ddd19-145">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddd19-145">-   eExitProcess</span></span><br /><span data-ttu-id="ddd19-146">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddd19-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="ddd19-147">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddd19-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ddd19-148">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ddd19-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ddd19-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="ddd19-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="ddd19-150">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddd19-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ddd19-151">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddd19-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ddd19-152">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddd19-152">-   eExitProcess</span></span><br /><span data-ttu-id="ddd19-153">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddd19-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="ddd19-154">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddd19-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ddd19-155">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ddd19-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ddd19-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="ddd19-156">OPR_ProcessExit</span></span>|<span data-ttu-id="ddd19-157">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddd19-157">-   eExitProcess</span></span><br /><span data-ttu-id="ddd19-158">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddd19-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="ddd19-159">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddd19-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ddd19-160">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ddd19-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddd19-161">要求</span><span class="sxs-lookup"><span data-stu-id="ddd19-161">Requirements</span></span>  
 <span data-ttu-id="ddd19-162">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddd19-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddd19-163">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ddd19-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ddd19-164">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ddd19-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddd19-165">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddd19-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd19-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddd19-166">See also</span></span>
- [<span data-ttu-id="ddd19-167">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="ddd19-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="ddd19-168">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="ddd19-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="ddd19-169">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="ddd19-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="ddd19-170">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="ddd19-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
