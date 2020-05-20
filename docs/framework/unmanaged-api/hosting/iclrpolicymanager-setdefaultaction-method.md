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
ms.openlocfilehash: c0d8b66c8b85710b0365bfc410188c81431720ff
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703437"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="01f7b-102">ICLRPolicyManager::SetDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="01f7b-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="01f7b-103">指定发生指定操作时公共语言运行时（CLR）应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="01f7b-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f7b-104">语法</span><span class="sxs-lookup"><span data-stu-id="01f7b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01f7b-105">参数</span><span class="sxs-lookup"><span data-stu-id="01f7b-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="01f7b-106">中[EClrOperation](eclroperation-enumeration.md)值之一，指示应为其自定义 CLR 行为的操作。</span><span class="sxs-lookup"><span data-stu-id="01f7b-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="01f7b-107">中[EPolicyAction](epolicyaction-enumeration.md)值之一，指示 CLR 在发生时应执行的策略操作 `operation` 。</span><span class="sxs-lookup"><span data-stu-id="01f7b-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01f7b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="01f7b-108">Return Value</span></span>  
  
|<span data-ttu-id="01f7b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01f7b-109">HRESULT</span></span>|<span data-ttu-id="01f7b-110">说明</span><span class="sxs-lookup"><span data-stu-id="01f7b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01f7b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="01f7b-111">S_OK</span></span>|<span data-ttu-id="01f7b-112">`SetDefaultAction`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="01f7b-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="01f7b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01f7b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01f7b-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="01f7b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01f7b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01f7b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01f7b-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="01f7b-116">The call timed out.</span></span>|  
|<span data-ttu-id="01f7b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01f7b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01f7b-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="01f7b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01f7b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01f7b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01f7b-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="01f7b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01f7b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01f7b-121">E_FAIL</span></span>|<span data-ttu-id="01f7b-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="01f7b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01f7b-123">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="01f7b-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01f7b-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="01f7b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="01f7b-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01f7b-125">E_INVALIDARG</span></span>|<span data-ttu-id="01f7b-126">为指定了无效的 `action` `operation` ，或者为提供的值无效 `operation` 。</span><span class="sxs-lookup"><span data-stu-id="01f7b-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01f7b-127">备注</span><span class="sxs-lookup"><span data-stu-id="01f7b-127">Remarks</span></span>  
 <span data-ttu-id="01f7b-128">并非所有策略操作值都可以指定为 CLR 操作的默认行为。</span><span class="sxs-lookup"><span data-stu-id="01f7b-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="01f7b-129">`SetDefaultAction`通常只能用于升级行为。</span><span class="sxs-lookup"><span data-stu-id="01f7b-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="01f7b-130">例如，主机可以指定线程中止进入强制线程中止，但不能指定相反的。</span><span class="sxs-lookup"><span data-stu-id="01f7b-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="01f7b-131">下表描述了 `action` 每个可能值的有效值 `operation` 。</span><span class="sxs-lookup"><span data-stu-id="01f7b-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="01f7b-132">值`operation`</span><span class="sxs-lookup"><span data-stu-id="01f7b-132">Value for `operation`</span></span>|<span data-ttu-id="01f7b-133">`action` 的有效值</span><span class="sxs-lookup"><span data-stu-id="01f7b-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="01f7b-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="01f7b-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="01f7b-135">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="01f7b-135">-   eAbortThread</span></span><br /><span data-ttu-id="01f7b-136">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="01f7b-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="01f7b-137">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01f7b-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="01f7b-138">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01f7b-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01f7b-139">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-139">-   eExitProcess</span></span><br /><span data-ttu-id="01f7b-140">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="01f7b-141">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01f7b-142">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01f7b-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01f7b-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="01f7b-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="01f7b-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="01f7b-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="01f7b-145">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="01f7b-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="01f7b-146">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01f7b-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="01f7b-147">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01f7b-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01f7b-148">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-148">-   eExitProcess</span></span><br /><span data-ttu-id="01f7b-149">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="01f7b-150">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01f7b-151">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01f7b-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01f7b-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="01f7b-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="01f7b-153">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01f7b-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="01f7b-154">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01f7b-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01f7b-155">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-155">-   eExitProcess</span></span><br /><span data-ttu-id="01f7b-156">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="01f7b-157">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01f7b-158">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01f7b-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01f7b-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="01f7b-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="01f7b-160">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01f7b-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01f7b-161">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-161">-   eExitProcess</span></span><br /><span data-ttu-id="01f7b-162">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="01f7b-163">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01f7b-164">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01f7b-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01f7b-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="01f7b-165">OPR_ProcessExit</span></span>|<span data-ttu-id="01f7b-166">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-166">-   eExitProcess</span></span><br /><span data-ttu-id="01f7b-167">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="01f7b-168">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01f7b-169">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01f7b-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01f7b-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="01f7b-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="01f7b-171">- eNoAction</span><span class="sxs-lookup"><span data-stu-id="01f7b-171">-   eNoAction</span></span><br /><span data-ttu-id="01f7b-172">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="01f7b-172">-   eAbortThread</span></span><br /><span data-ttu-id="01f7b-173">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="01f7b-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="01f7b-174">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01f7b-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="01f7b-175">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01f7b-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01f7b-176">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-176">-   eExitProcess</span></span><br /><span data-ttu-id="01f7b-177">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="01f7b-178">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01f7b-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01f7b-179">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01f7b-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01f7b-180">要求</span><span class="sxs-lookup"><span data-stu-id="01f7b-180">Requirements</span></span>  
 <span data-ttu-id="01f7b-181">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01f7b-181">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01f7b-182">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="01f7b-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01f7b-183">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="01f7b-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01f7b-184">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01f7b-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f7b-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01f7b-185">See also</span></span>

- [<span data-ttu-id="01f7b-186">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="01f7b-186">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="01f7b-187">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="01f7b-187">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="01f7b-188">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="01f7b-188">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
