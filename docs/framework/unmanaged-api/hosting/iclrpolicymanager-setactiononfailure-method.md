---
title: "ICLRPolicyManager::SetActionOnFailure 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5dc8e27ed1a5701886c3583a7515e4212f490208
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="cbf7f-102">ICLRPolicyManager::SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="cbf7f-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="cbf7f-103">指定公共语言运行时 (CLR) 在发生指定的故障时应采取的策略操作。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbf7f-104">语法</span><span class="sxs-lookup"><span data-stu-id="cbf7f-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbf7f-105">参数</span><span class="sxs-lookup"><span data-stu-id="cbf7f-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="cbf7f-106">[in]之一[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值，指示为其执行操作的失败类型。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="cbf7f-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示在发生故障时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="cbf7f-108">有关支持的值的列表，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbf7f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="cbf7f-109">Return Value</span></span>  
  
|<span data-ttu-id="cbf7f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cbf7f-110">HRESULT</span></span>|<span data-ttu-id="cbf7f-111">描述</span><span class="sxs-lookup"><span data-stu-id="cbf7f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cbf7f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="cbf7f-112">S_OK</span></span>|<span data-ttu-id="cbf7f-113">`SetActionOnFailure`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="cbf7f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cbf7f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cbf7f-115">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cbf7f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cbf7f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cbf7f-117">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-117">The call timed out.</span></span>|  
|<span data-ttu-id="cbf7f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cbf7f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cbf7f-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cbf7f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cbf7f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cbf7f-121">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cbf7f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cbf7f-122">E_FAIL</span></span>|<span data-ttu-id="cbf7f-123">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cbf7f-124">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cbf7f-125">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cbf7f-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cbf7f-126">E_INVALIDARG</span></span>|<span data-ttu-id="cbf7f-127">策略操作不能设置为指定的操作，或为操作指定了无效策略操作。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbf7f-128">备注</span><span class="sxs-lookup"><span data-stu-id="cbf7f-128">Remarks</span></span>  
 <span data-ttu-id="cbf7f-129">默认情况下，CLR 在它无法分配某个资源例如内存时引发异常。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="cbf7f-130">`SetActionOnFailure`允许主机通过指定要在失败时执行的策略操作重写此行为。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="cbf7f-131">下表显示的组合[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)和[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)支持的值。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="cbf7f-132">(中省略 FAIL_ 前缀[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值。)</span><span class="sxs-lookup"><span data-stu-id="cbf7f-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="cbf7f-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="cbf7f-133">NonCriticalResource</span></span>|<span data-ttu-id="cbf7f-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="cbf7f-134">CriticalResource</span></span>|<span data-ttu-id="cbf7f-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="cbf7f-135">FatalRuntime</span></span>|<span data-ttu-id="cbf7f-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="cbf7f-136">OrphanedLock</span></span>|<span data-ttu-id="cbf7f-137">堆栈溢出</span><span class="sxs-lookup"><span data-stu-id="cbf7f-137">StackOverflow</span></span>|<span data-ttu-id="cbf7f-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="cbf7f-138">AccessViolation</span></span>|<span data-ttu-id="cbf7f-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="cbf7f-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="cbf7f-140">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-140">X</span></span>|<span data-ttu-id="cbf7f-141">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-141">X</span></span>||||<span data-ttu-id="cbf7f-142">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-142">N/A</span></span>||  
|<span data-ttu-id="cbf7f-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="cbf7f-143">eThrowException</span></span>|<span data-ttu-id="cbf7f-144">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-144">X</span></span>|<span data-ttu-id="cbf7f-145">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-145">X</span></span>||||<span data-ttu-id="cbf7f-146">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="cbf7f-147">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-147">X</span></span>|<span data-ttu-id="cbf7f-148">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-148">X</span></span>||||<span data-ttu-id="cbf7f-149">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-149">N/A</span></span>|<span data-ttu-id="cbf7f-150">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="cbf7f-151">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-151">X</span></span>|<span data-ttu-id="cbf7f-152">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-152">X</span></span>||||<span data-ttu-id="cbf7f-153">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-153">N/A</span></span>|<span data-ttu-id="cbf7f-154">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="cbf7f-155">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-155">X</span></span>|<span data-ttu-id="cbf7f-156">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-156">X</span></span>||<span data-ttu-id="cbf7f-157">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-157">X</span></span>||<span data-ttu-id="cbf7f-158">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-158">N/A</span></span>|<span data-ttu-id="cbf7f-159">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="cbf7f-160">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-160">X</span></span>|<span data-ttu-id="cbf7f-161">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-161">X</span></span>||<span data-ttu-id="cbf7f-162">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-162">X</span></span>|<span data-ttu-id="cbf7f-163">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-163">X</span></span>|<span data-ttu-id="cbf7f-164">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-164">N/A</span></span>|<span data-ttu-id="cbf7f-165">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="cbf7f-166">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-166">X</span></span>|<span data-ttu-id="cbf7f-167">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-167">X</span></span>||<span data-ttu-id="cbf7f-168">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-168">X</span></span>|<span data-ttu-id="cbf7f-169">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-169">X</span></span>|<span data-ttu-id="cbf7f-170">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-170">N/A</span></span>|<span data-ttu-id="cbf7f-171">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-171">X</span></span>|  
|<span data-ttu-id="cbf7f-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="cbf7f-172">eFastExitProcess</span></span>|<span data-ttu-id="cbf7f-173">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-173">X</span></span>|<span data-ttu-id="cbf7f-174">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-174">X</span></span>||<span data-ttu-id="cbf7f-175">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-175">X</span></span>|<span data-ttu-id="cbf7f-176">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-176">X</span></span>|<span data-ttu-id="cbf7f-177">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="cbf7f-178">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-178">X</span></span>|<span data-ttu-id="cbf7f-179">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-179">X</span></span>|<span data-ttu-id="cbf7f-180">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-180">X</span></span>|<span data-ttu-id="cbf7f-181">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-181">X</span></span>|<span data-ttu-id="cbf7f-182">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-182">X</span></span>|<span data-ttu-id="cbf7f-183">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="cbf7f-184">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-184">X</span></span>|<span data-ttu-id="cbf7f-185">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-185">X</span></span>|<span data-ttu-id="cbf7f-186">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-186">X</span></span>|<span data-ttu-id="cbf7f-187">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-187">X</span></span>|<span data-ttu-id="cbf7f-188">X</span><span class="sxs-lookup"><span data-stu-id="cbf7f-188">X</span></span>|<span data-ttu-id="cbf7f-189">不可用</span><span class="sxs-lookup"><span data-stu-id="cbf7f-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="cbf7f-190">要求</span><span class="sxs-lookup"><span data-stu-id="cbf7f-190">Requirements</span></span>  
 <span data-ttu-id="cbf7f-191">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cbf7f-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbf7f-192">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cbf7f-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbf7f-193">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cbf7f-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbf7f-194">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbf7f-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf7f-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbf7f-195">See Also</span></span>  
 [<span data-ttu-id="cbf7f-196">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="cbf7f-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="cbf7f-197">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="cbf7f-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="cbf7f-198">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="cbf7f-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="cbf7f-199">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="cbf7f-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
