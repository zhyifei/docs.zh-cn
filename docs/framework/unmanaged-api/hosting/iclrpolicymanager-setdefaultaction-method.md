---
title: "ICLRPolicyManager::SetDefaultAction 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 751853aaf4322c15b44bb9b912d293a081c24ba8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="d67d8-102">ICLRPolicyManager::SetDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="d67d8-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="d67d8-103">指定公共语言运行时 (CLR) 指定的操作发生时应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="d67d8-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d67d8-104">语法</span><span class="sxs-lookup"><span data-stu-id="d67d8-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d67d8-105">参数</span><span class="sxs-lookup"><span data-stu-id="d67d8-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="d67d8-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，指示应为哪些 CLR 自定义行为的操作。</span><span class="sxs-lookup"><span data-stu-id="d67d8-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="d67d8-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示时，应采取的策略措施 CLR`operation`时发生。</span><span class="sxs-lookup"><span data-stu-id="d67d8-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d67d8-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d67d8-108">Return Value</span></span>  
  
|<span data-ttu-id="d67d8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d67d8-109">HRESULT</span></span>|<span data-ttu-id="d67d8-110">描述</span><span class="sxs-lookup"><span data-stu-id="d67d8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d67d8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d67d8-111">S_OK</span></span>|<span data-ttu-id="d67d8-112">`SetDefaultAction`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d67d8-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="d67d8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d67d8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d67d8-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d67d8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d67d8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d67d8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d67d8-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="d67d8-116">The call timed out.</span></span>|  
|<span data-ttu-id="d67d8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d67d8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d67d8-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d67d8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d67d8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d67d8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d67d8-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d67d8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d67d8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d67d8-121">E_FAIL</span></span>|<span data-ttu-id="d67d8-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d67d8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d67d8-123">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="d67d8-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d67d8-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d67d8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d67d8-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d67d8-125">E_INVALIDARG</span></span>|<span data-ttu-id="d67d8-126">无效`action`为指定`operation`，或为提供的无效值`operation`。</span><span class="sxs-lookup"><span data-stu-id="d67d8-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d67d8-127">备注</span><span class="sxs-lookup"><span data-stu-id="d67d8-127">Remarks</span></span>  
 <span data-ttu-id="d67d8-128">并非所有策略操作值可以都指定为 CLR 操作的默认行为。</span><span class="sxs-lookup"><span data-stu-id="d67d8-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="d67d8-129">`SetDefaultAction`可以通常仅用于提升行为。</span><span class="sxs-lookup"><span data-stu-id="d67d8-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="d67d8-130">例如，主机可以指定线程中止转变为强制线程终止，但不能指定相反。</span><span class="sxs-lookup"><span data-stu-id="d67d8-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="d67d8-131">下表描述了有效`action`对每个可能的值`operation`值。</span><span class="sxs-lookup"><span data-stu-id="d67d8-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="d67d8-132">值`operation`</span><span class="sxs-lookup"><span data-stu-id="d67d8-132">Value for `operation`</span></span>|<span data-ttu-id="d67d8-133">有效值为`action`</span><span class="sxs-lookup"><span data-stu-id="d67d8-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="d67d8-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="d67d8-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="d67d8-135">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="d67d8-135">-   eAbortThread</span></span><br /><span data-ttu-id="d67d8-136">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="d67d8-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="d67d8-137">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d67d8-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="d67d8-138">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d67d8-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="d67d8-139">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-139">-   eExitProcess</span></span><br /><span data-ttu-id="d67d8-140">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="d67d8-141">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d67d8-142">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d67d8-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="d67d8-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d67d8-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="d67d8-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d67d8-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="d67d8-145">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="d67d8-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="d67d8-146">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d67d8-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="d67d8-147">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d67d8-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="d67d8-148">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-148">-   eExitProcess</span></span><br /><span data-ttu-id="d67d8-149">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="d67d8-150">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d67d8-151">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d67d8-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="d67d8-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="d67d8-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="d67d8-153">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d67d8-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="d67d8-154">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d67d8-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="d67d8-155">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-155">-   eExitProcess</span></span><br /><span data-ttu-id="d67d8-156">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="d67d8-157">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d67d8-158">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d67d8-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="d67d8-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="d67d8-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="d67d8-160">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d67d8-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="d67d8-161">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-161">-   eExitProcess</span></span><br /><span data-ttu-id="d67d8-162">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="d67d8-163">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d67d8-164">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d67d8-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="d67d8-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="d67d8-165">OPR_ProcessExit</span></span>|<span data-ttu-id="d67d8-166">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-166">-   eExitProcess</span></span><br /><span data-ttu-id="d67d8-167">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="d67d8-168">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d67d8-169">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d67d8-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="d67d8-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="d67d8-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="d67d8-171">-eNoAction</span><span class="sxs-lookup"><span data-stu-id="d67d8-171">-   eNoAction</span></span><br /><span data-ttu-id="d67d8-172">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="d67d8-172">-   eAbortThread</span></span><br /><span data-ttu-id="d67d8-173">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="d67d8-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="d67d8-174">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d67d8-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="d67d8-175">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d67d8-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="d67d8-176">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-176">-   eExitProcess</span></span><br /><span data-ttu-id="d67d8-177">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="d67d8-178">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d67d8-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d67d8-179">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d67d8-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d67d8-180">惠?</span><span class="sxs-lookup"><span data-stu-id="d67d8-180">Requirements</span></span>  
 <span data-ttu-id="d67d8-181">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d67d8-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d67d8-182">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d67d8-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d67d8-183">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d67d8-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d67d8-184">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d67d8-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d67d8-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="d67d8-185">See Also</span></span>  
 [<span data-ttu-id="d67d8-186">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="d67d8-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="d67d8-187">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="d67d8-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="d67d8-188">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="d67d8-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
