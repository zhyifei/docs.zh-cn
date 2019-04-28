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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638796"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="dbf30-102">ICLRPolicyManager::SetDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="dbf30-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="dbf30-103">指定公共语言运行时 (CLR) 指定的操作发生时应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="dbf30-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbf30-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbf30-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbf30-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbf30-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="dbf30-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，它指示哪个 CLR 的行为进行自定义的操作。</span><span class="sxs-lookup"><span data-stu-id="dbf30-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="dbf30-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，它指示时，应采取的策略操作 CLR`operation`时发生。</span><span class="sxs-lookup"><span data-stu-id="dbf30-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbf30-108">返回值</span><span class="sxs-lookup"><span data-stu-id="dbf30-108">Return Value</span></span>  
  
|<span data-ttu-id="dbf30-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbf30-109">HRESULT</span></span>|<span data-ttu-id="dbf30-110">描述</span><span class="sxs-lookup"><span data-stu-id="dbf30-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbf30-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbf30-111">S_OK</span></span>|<span data-ttu-id="dbf30-112">`SetDefaultAction` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="dbf30-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="dbf30-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dbf30-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dbf30-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="dbf30-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dbf30-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dbf30-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dbf30-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="dbf30-116">The call timed out.</span></span>|  
|<span data-ttu-id="dbf30-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dbf30-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dbf30-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="dbf30-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dbf30-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dbf30-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dbf30-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="dbf30-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dbf30-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbf30-121">E_FAIL</span></span>|<span data-ttu-id="dbf30-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="dbf30-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dbf30-123">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="dbf30-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dbf30-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="dbf30-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dbf30-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dbf30-125">E_INVALIDARG</span></span>|<span data-ttu-id="dbf30-126">无效`action`为指定`operation`，或对于提供的值无效`operation`。</span><span class="sxs-lookup"><span data-stu-id="dbf30-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbf30-127">备注</span><span class="sxs-lookup"><span data-stu-id="dbf30-127">Remarks</span></span>  
 <span data-ttu-id="dbf30-128">并非所有策略操作值可以都指定为对于 CLR 操作的默认行为。</span><span class="sxs-lookup"><span data-stu-id="dbf30-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="dbf30-129">`SetDefaultAction` 通常可只是为了提升行为。</span><span class="sxs-lookup"><span data-stu-id="dbf30-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="dbf30-130">例如，主机可以指定线程中止转变为强制线程终止，但不能指定相反。</span><span class="sxs-lookup"><span data-stu-id="dbf30-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="dbf30-131">下表列出了有效`action`对每个可能的值`operation`值。</span><span class="sxs-lookup"><span data-stu-id="dbf30-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="dbf30-132">值 `operation`</span><span class="sxs-lookup"><span data-stu-id="dbf30-132">Value for `operation`</span></span>|<span data-ttu-id="dbf30-133">有效值 `action`</span><span class="sxs-lookup"><span data-stu-id="dbf30-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="dbf30-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="dbf30-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="dbf30-135">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="dbf30-135">-   eAbortThread</span></span><br /><span data-ttu-id="dbf30-136">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="dbf30-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="dbf30-137">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dbf30-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="dbf30-138">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dbf30-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="dbf30-139">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-139">-   eExitProcess</span></span><br /><span data-ttu-id="dbf30-140">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="dbf30-141">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="dbf30-142">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="dbf30-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="dbf30-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="dbf30-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="dbf30-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="dbf30-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="dbf30-145">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="dbf30-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="dbf30-146">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dbf30-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="dbf30-147">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dbf30-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="dbf30-148">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-148">-   eExitProcess</span></span><br /><span data-ttu-id="dbf30-149">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="dbf30-150">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="dbf30-151">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="dbf30-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="dbf30-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="dbf30-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="dbf30-153">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dbf30-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="dbf30-154">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dbf30-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="dbf30-155">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-155">-   eExitProcess</span></span><br /><span data-ttu-id="dbf30-156">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="dbf30-157">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="dbf30-158">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="dbf30-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="dbf30-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="dbf30-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="dbf30-160">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dbf30-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="dbf30-161">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-161">-   eExitProcess</span></span><br /><span data-ttu-id="dbf30-162">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="dbf30-163">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="dbf30-164">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="dbf30-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="dbf30-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="dbf30-165">OPR_ProcessExit</span></span>|<span data-ttu-id="dbf30-166">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-166">-   eExitProcess</span></span><br /><span data-ttu-id="dbf30-167">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="dbf30-168">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="dbf30-169">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="dbf30-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="dbf30-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="dbf30-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="dbf30-171">-   eNoAction</span><span class="sxs-lookup"><span data-stu-id="dbf30-171">-   eNoAction</span></span><br /><span data-ttu-id="dbf30-172">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="dbf30-172">-   eAbortThread</span></span><br /><span data-ttu-id="dbf30-173">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="dbf30-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="dbf30-174">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dbf30-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="dbf30-175">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dbf30-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="dbf30-176">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-176">-   eExitProcess</span></span><br /><span data-ttu-id="dbf30-177">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="dbf30-178">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="dbf30-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="dbf30-179">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="dbf30-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dbf30-180">要求</span><span class="sxs-lookup"><span data-stu-id="dbf30-180">Requirements</span></span>  
 <span data-ttu-id="dbf30-181">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbf30-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbf30-182">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dbf30-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbf30-183">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dbf30-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbf30-184">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbf30-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf30-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbf30-185">See also</span></span>

- [<span data-ttu-id="dbf30-186">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="dbf30-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="dbf30-187">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="dbf30-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="dbf30-188">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="dbf30-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
