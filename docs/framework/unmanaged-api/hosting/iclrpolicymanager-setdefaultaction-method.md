---
title: ICLRPolicyManager::SetDefaultAction 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69a8d0cb09e057d4bcc3c9713c5b16c22fa45c5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602957"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="a68fa-102">ICLRPolicyManager::SetDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="a68fa-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="a68fa-103">指定公共语言运行时 (CLR) 指定的操作发生时应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="a68fa-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a68fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="a68fa-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a68fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="a68fa-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="a68fa-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，它指示哪个 CLR 的行为进行自定义的操作。</span><span class="sxs-lookup"><span data-stu-id="a68fa-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="a68fa-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，它指示时，应采取的策略操作 CLR`operation`时发生。</span><span class="sxs-lookup"><span data-stu-id="a68fa-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a68fa-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a68fa-108">Return Value</span></span>  
  
|<span data-ttu-id="a68fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a68fa-109">HRESULT</span></span>|<span data-ttu-id="a68fa-110">描述</span><span class="sxs-lookup"><span data-stu-id="a68fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a68fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a68fa-111">S_OK</span></span>|<span data-ttu-id="a68fa-112">`SetDefaultAction` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a68fa-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="a68fa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a68fa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a68fa-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a68fa-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a68fa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a68fa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a68fa-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="a68fa-116">The call timed out.</span></span>|  
|<span data-ttu-id="a68fa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a68fa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a68fa-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a68fa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a68fa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a68fa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a68fa-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="a68fa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a68fa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a68fa-121">E_FAIL</span></span>|<span data-ttu-id="a68fa-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a68fa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a68fa-123">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="a68fa-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a68fa-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a68fa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a68fa-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a68fa-125">E_INVALIDARG</span></span>|<span data-ttu-id="a68fa-126">无效`action`为指定`operation`，或对于提供的值无效`operation`。</span><span class="sxs-lookup"><span data-stu-id="a68fa-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a68fa-127">备注</span><span class="sxs-lookup"><span data-stu-id="a68fa-127">Remarks</span></span>  
 <span data-ttu-id="a68fa-128">并非所有策略操作值可以都指定为对于 CLR 操作的默认行为。</span><span class="sxs-lookup"><span data-stu-id="a68fa-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="a68fa-129">`SetDefaultAction` 通常可只是为了提升行为。</span><span class="sxs-lookup"><span data-stu-id="a68fa-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="a68fa-130">例如，主机可以指定线程中止转变为强制线程终止，但不能指定相反。</span><span class="sxs-lookup"><span data-stu-id="a68fa-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="a68fa-131">下表列出了有效`action`对每个可能的值`operation`值。</span><span class="sxs-lookup"><span data-stu-id="a68fa-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="a68fa-132">值 `operation`</span><span class="sxs-lookup"><span data-stu-id="a68fa-132">Value for `operation`</span></span>|<span data-ttu-id="a68fa-133">有效值 `action`</span><span class="sxs-lookup"><span data-stu-id="a68fa-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="a68fa-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="a68fa-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="a68fa-135">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="a68fa-135">-   eAbortThread</span></span><br /><span data-ttu-id="a68fa-136">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="a68fa-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="a68fa-137">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a68fa-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="a68fa-138">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a68fa-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="a68fa-139">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-139">-   eExitProcess</span></span><br /><span data-ttu-id="a68fa-140">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="a68fa-141">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="a68fa-142">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="a68fa-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="a68fa-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a68fa-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="a68fa-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a68fa-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="a68fa-145">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="a68fa-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="a68fa-146">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a68fa-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="a68fa-147">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a68fa-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="a68fa-148">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-148">-   eExitProcess</span></span><br /><span data-ttu-id="a68fa-149">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="a68fa-150">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="a68fa-151">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="a68fa-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="a68fa-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="a68fa-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="a68fa-153">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a68fa-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="a68fa-154">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a68fa-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="a68fa-155">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-155">-   eExitProcess</span></span><br /><span data-ttu-id="a68fa-156">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="a68fa-157">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="a68fa-158">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="a68fa-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="a68fa-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="a68fa-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="a68fa-160">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a68fa-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="a68fa-161">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-161">-   eExitProcess</span></span><br /><span data-ttu-id="a68fa-162">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="a68fa-163">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="a68fa-164">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="a68fa-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="a68fa-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="a68fa-165">OPR_ProcessExit</span></span>|<span data-ttu-id="a68fa-166">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-166">-   eExitProcess</span></span><br /><span data-ttu-id="a68fa-167">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="a68fa-168">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="a68fa-169">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="a68fa-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="a68fa-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="a68fa-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="a68fa-171">-   eNoAction</span><span class="sxs-lookup"><span data-stu-id="a68fa-171">-   eNoAction</span></span><br /><span data-ttu-id="a68fa-172">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="a68fa-172">-   eAbortThread</span></span><br /><span data-ttu-id="a68fa-173">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="a68fa-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="a68fa-174">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a68fa-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="a68fa-175">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a68fa-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="a68fa-176">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-176">-   eExitProcess</span></span><br /><span data-ttu-id="a68fa-177">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="a68fa-178">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="a68fa-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="a68fa-179">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="a68fa-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a68fa-180">要求</span><span class="sxs-lookup"><span data-stu-id="a68fa-180">Requirements</span></span>  
 <span data-ttu-id="a68fa-181">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a68fa-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a68fa-182">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a68fa-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a68fa-183">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a68fa-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a68fa-184">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a68fa-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a68fa-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="a68fa-185">See also</span></span>
- [<span data-ttu-id="a68fa-186">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="a68fa-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="a68fa-187">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="a68fa-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="a68fa-188">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="a68fa-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
