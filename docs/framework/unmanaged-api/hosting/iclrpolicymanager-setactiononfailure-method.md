---
title: ICLRPolicyManager::SetActionOnFailure 方法
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebfe02774aa8cea74c17340d63f930cf87a6fa27
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478461"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="dce5e-102">ICLRPolicyManager::SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="dce5e-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="dce5e-103">指定公共语言运行时 (CLR) 指定的故障发生时应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="dce5e-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dce5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="dce5e-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dce5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="dce5e-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="dce5e-106">[in]之一[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值，它指示要为其执行操作失败的类型。</span><span class="sxs-lookup"><span data-stu-id="dce5e-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="dce5e-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示出现故障时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="dce5e-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="dce5e-108">有关支持的值的列表，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="dce5e-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dce5e-109">返回值</span><span class="sxs-lookup"><span data-stu-id="dce5e-109">Return Value</span></span>  
  
|<span data-ttu-id="dce5e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dce5e-110">HRESULT</span></span>|<span data-ttu-id="dce5e-111">描述</span><span class="sxs-lookup"><span data-stu-id="dce5e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dce5e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="dce5e-112">S_OK</span></span>|<span data-ttu-id="dce5e-113">`SetActionOnFailure` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="dce5e-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="dce5e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dce5e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dce5e-115">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="dce5e-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dce5e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dce5e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dce5e-117">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="dce5e-117">The call timed out.</span></span>|  
|<span data-ttu-id="dce5e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dce5e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dce5e-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="dce5e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dce5e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dce5e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dce5e-121">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="dce5e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dce5e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dce5e-122">E_FAIL</span></span>|<span data-ttu-id="dce5e-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="dce5e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dce5e-124">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="dce5e-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dce5e-125">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="dce5e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dce5e-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dce5e-126">E_INVALIDARG</span></span>|<span data-ttu-id="dce5e-127">策略操作不能设置为指定的操作，或为操作指定了无效的策略操作。</span><span class="sxs-lookup"><span data-stu-id="dce5e-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dce5e-128">备注</span><span class="sxs-lookup"><span data-stu-id="dce5e-128">Remarks</span></span>  
 <span data-ttu-id="dce5e-129">默认情况下，CLR 无法分配内存等资源时引发异常。</span><span class="sxs-lookup"><span data-stu-id="dce5e-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="dce5e-130">`SetActionOnFailure` 允许重写此行为，通过指定要在失败时执行的策略操作主机。</span><span class="sxs-lookup"><span data-stu-id="dce5e-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="dce5e-131">下表显示了的组合[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)并[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)支持的值。</span><span class="sxs-lookup"><span data-stu-id="dce5e-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="dce5e-132">(从省略 FAIL_ 前缀[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值。)</span><span class="sxs-lookup"><span data-stu-id="dce5e-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="dce5e-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="dce5e-133">NonCriticalResource</span></span>|<span data-ttu-id="dce5e-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="dce5e-134">CriticalResource</span></span>|<span data-ttu-id="dce5e-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="dce5e-135">FatalRuntime</span></span>|<span data-ttu-id="dce5e-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="dce5e-136">OrphanedLock</span></span>|<span data-ttu-id="dce5e-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="dce5e-137">StackOverflow</span></span>|<span data-ttu-id="dce5e-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="dce5e-138">AccessViolation</span></span>|<span data-ttu-id="dce5e-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="dce5e-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="dce5e-140">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-140">X</span></span>|<span data-ttu-id="dce5e-141">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-141">X</span></span>||||<span data-ttu-id="dce5e-142">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-142">N/A</span></span>||  
|<span data-ttu-id="dce5e-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="dce5e-143">eThrowException</span></span>|<span data-ttu-id="dce5e-144">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-144">X</span></span>|<span data-ttu-id="dce5e-145">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-145">X</span></span>||||<span data-ttu-id="dce5e-146">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="dce5e-147">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-147">X</span></span>|<span data-ttu-id="dce5e-148">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-148">X</span></span>||||<span data-ttu-id="dce5e-149">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-149">N/A</span></span>|<span data-ttu-id="dce5e-150">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="dce5e-151">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-151">X</span></span>|<span data-ttu-id="dce5e-152">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-152">X</span></span>||||<span data-ttu-id="dce5e-153">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-153">N/A</span></span>|<span data-ttu-id="dce5e-154">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="dce5e-155">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-155">X</span></span>|<span data-ttu-id="dce5e-156">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-156">X</span></span>||<span data-ttu-id="dce5e-157">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-157">X</span></span>||<span data-ttu-id="dce5e-158">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-158">N/A</span></span>|<span data-ttu-id="dce5e-159">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="dce5e-160">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-160">X</span></span>|<span data-ttu-id="dce5e-161">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-161">X</span></span>||<span data-ttu-id="dce5e-162">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-162">X</span></span>|<span data-ttu-id="dce5e-163">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-163">X</span></span>|<span data-ttu-id="dce5e-164">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-164">N/A</span></span>|<span data-ttu-id="dce5e-165">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="dce5e-166">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-166">X</span></span>|<span data-ttu-id="dce5e-167">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-167">X</span></span>||<span data-ttu-id="dce5e-168">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-168">X</span></span>|<span data-ttu-id="dce5e-169">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-169">X</span></span>|<span data-ttu-id="dce5e-170">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-170">N/A</span></span>|<span data-ttu-id="dce5e-171">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-171">X</span></span>|  
|<span data-ttu-id="dce5e-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dce5e-172">eFastExitProcess</span></span>|<span data-ttu-id="dce5e-173">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-173">X</span></span>|<span data-ttu-id="dce5e-174">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-174">X</span></span>||<span data-ttu-id="dce5e-175">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-175">X</span></span>|<span data-ttu-id="dce5e-176">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-176">X</span></span>|<span data-ttu-id="dce5e-177">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="dce5e-178">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-178">X</span></span>|<span data-ttu-id="dce5e-179">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-179">X</span></span>|<span data-ttu-id="dce5e-180">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-180">X</span></span>|<span data-ttu-id="dce5e-181">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-181">X</span></span>|<span data-ttu-id="dce5e-182">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-182">X</span></span>|<span data-ttu-id="dce5e-183">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="dce5e-184">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-184">X</span></span>|<span data-ttu-id="dce5e-185">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-185">X</span></span>|<span data-ttu-id="dce5e-186">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-186">X</span></span>|<span data-ttu-id="dce5e-187">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-187">X</span></span>|<span data-ttu-id="dce5e-188">X</span><span class="sxs-lookup"><span data-stu-id="dce5e-188">X</span></span>|<span data-ttu-id="dce5e-189">不可用</span><span class="sxs-lookup"><span data-stu-id="dce5e-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="dce5e-190">要求</span><span class="sxs-lookup"><span data-stu-id="dce5e-190">Requirements</span></span>  
 <span data-ttu-id="dce5e-191">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dce5e-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dce5e-192">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dce5e-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dce5e-193">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dce5e-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dce5e-194">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dce5e-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce5e-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="dce5e-195">See also</span></span>
- [<span data-ttu-id="dce5e-196">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="dce5e-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="dce5e-197">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="dce5e-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="dce5e-198">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="dce5e-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="dce5e-199">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="dce5e-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
