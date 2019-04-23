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
ms.openlocfilehash: 3d339fbadc3260d20fac848ad7f1a9031c3443aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154656"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="ddabd-102">ICLRPolicyManager::SetDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="ddabd-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="ddabd-103">指定公共语言运行时 (CLR) 指定的操作发生时应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="ddabd-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddabd-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddabd-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddabd-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddabd-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="ddabd-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，它指示哪个 CLR 的行为进行自定义的操作。</span><span class="sxs-lookup"><span data-stu-id="ddabd-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="ddabd-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，它指示时，应采取的策略操作 CLR`operation`时发生。</span><span class="sxs-lookup"><span data-stu-id="ddabd-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddabd-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ddabd-108">Return Value</span></span>  
  
|<span data-ttu-id="ddabd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ddabd-109">HRESULT</span></span>|<span data-ttu-id="ddabd-110">描述</span><span class="sxs-lookup"><span data-stu-id="ddabd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ddabd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ddabd-111">S_OK</span></span>|<span data-ttu-id="ddabd-112">`SetDefaultAction` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ddabd-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="ddabd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ddabd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ddabd-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ddabd-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ddabd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ddabd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ddabd-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="ddabd-116">The call timed out.</span></span>|  
|<span data-ttu-id="ddabd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ddabd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ddabd-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ddabd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ddabd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ddabd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ddabd-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ddabd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ddabd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ddabd-121">E_FAIL</span></span>|<span data-ttu-id="ddabd-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ddabd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ddabd-123">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="ddabd-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ddabd-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ddabd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ddabd-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ddabd-125">E_INVALIDARG</span></span>|<span data-ttu-id="ddabd-126">无效`action`为指定`operation`，或对于提供的值无效`operation`。</span><span class="sxs-lookup"><span data-stu-id="ddabd-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddabd-127">备注</span><span class="sxs-lookup"><span data-stu-id="ddabd-127">Remarks</span></span>  
 <span data-ttu-id="ddabd-128">并非所有策略操作值可以都指定为对于 CLR 操作的默认行为。</span><span class="sxs-lookup"><span data-stu-id="ddabd-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="ddabd-129">`SetDefaultAction` 通常可只是为了提升行为。</span><span class="sxs-lookup"><span data-stu-id="ddabd-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="ddabd-130">例如，主机可以指定线程中止转变为强制线程终止，但不能指定相反。</span><span class="sxs-lookup"><span data-stu-id="ddabd-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="ddabd-131">下表列出了有效`action`对每个可能的值`operation`值。</span><span class="sxs-lookup"><span data-stu-id="ddabd-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="ddabd-132">值 `operation`</span><span class="sxs-lookup"><span data-stu-id="ddabd-132">Value for `operation`</span></span>|<span data-ttu-id="ddabd-133">有效值 `action`</span><span class="sxs-lookup"><span data-stu-id="ddabd-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="ddabd-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="ddabd-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="ddabd-135">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="ddabd-135">-   eAbortThread</span></span><br /><span data-ttu-id="ddabd-136">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="ddabd-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="ddabd-137">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddabd-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ddabd-138">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddabd-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ddabd-139">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-139">-   eExitProcess</span></span><br /><span data-ttu-id="ddabd-140">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="ddabd-141">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ddabd-142">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ddabd-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ddabd-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ddabd-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="ddabd-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ddabd-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="ddabd-145">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="ddabd-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="ddabd-146">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddabd-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ddabd-147">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddabd-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ddabd-148">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-148">-   eExitProcess</span></span><br /><span data-ttu-id="ddabd-149">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="ddabd-150">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ddabd-151">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ddabd-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ddabd-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="ddabd-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="ddabd-153">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddabd-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ddabd-154">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddabd-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ddabd-155">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-155">-   eExitProcess</span></span><br /><span data-ttu-id="ddabd-156">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="ddabd-157">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ddabd-158">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ddabd-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ddabd-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="ddabd-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="ddabd-160">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddabd-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ddabd-161">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-161">-   eExitProcess</span></span><br /><span data-ttu-id="ddabd-162">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="ddabd-163">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ddabd-164">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ddabd-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ddabd-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="ddabd-165">OPR_ProcessExit</span></span>|<span data-ttu-id="ddabd-166">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-166">-   eExitProcess</span></span><br /><span data-ttu-id="ddabd-167">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="ddabd-168">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ddabd-169">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ddabd-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ddabd-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="ddabd-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="ddabd-171">-   eNoAction</span><span class="sxs-lookup"><span data-stu-id="ddabd-171">-   eNoAction</span></span><br /><span data-ttu-id="ddabd-172">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="ddabd-172">-   eAbortThread</span></span><br /><span data-ttu-id="ddabd-173">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="ddabd-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="ddabd-174">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddabd-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ddabd-175">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ddabd-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ddabd-176">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-176">-   eExitProcess</span></span><br /><span data-ttu-id="ddabd-177">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="ddabd-178">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ddabd-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ddabd-179">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ddabd-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddabd-180">要求</span><span class="sxs-lookup"><span data-stu-id="ddabd-180">Requirements</span></span>  
 <span data-ttu-id="ddabd-181">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddabd-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddabd-182">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ddabd-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ddabd-183">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ddabd-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddabd-184">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddabd-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddabd-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddabd-185">See also</span></span>

- [<span data-ttu-id="ddabd-186">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="ddabd-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="ddabd-187">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="ddabd-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="ddabd-188">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="ddabd-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
