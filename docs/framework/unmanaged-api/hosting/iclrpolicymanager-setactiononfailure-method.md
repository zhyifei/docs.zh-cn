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
ms.openlocfilehash: bc3616b2cec0fa951df745e3c5f0468f74ab82bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435924"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="049d0-102">ICLRPolicyManager::SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="049d0-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="049d0-103">指定公共语言运行时 (CLR) 在发生指定的故障时应采取的策略操作。</span><span class="sxs-lookup"><span data-stu-id="049d0-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="049d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="049d0-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="049d0-105">参数</span><span class="sxs-lookup"><span data-stu-id="049d0-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="049d0-106">[in]之一[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值，指示为其执行操作的失败类型。</span><span class="sxs-lookup"><span data-stu-id="049d0-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="049d0-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示在发生故障时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="049d0-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="049d0-108">有关支持的值的列表，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="049d0-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="049d0-109">返回值</span><span class="sxs-lookup"><span data-stu-id="049d0-109">Return Value</span></span>  
  
|<span data-ttu-id="049d0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="049d0-110">HRESULT</span></span>|<span data-ttu-id="049d0-111">描述</span><span class="sxs-lookup"><span data-stu-id="049d0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="049d0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="049d0-112">S_OK</span></span>|<span data-ttu-id="049d0-113">`SetActionOnFailure` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="049d0-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="049d0-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="049d0-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="049d0-115">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="049d0-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="049d0-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="049d0-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="049d0-117">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="049d0-117">The call timed out.</span></span>|  
|<span data-ttu-id="049d0-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="049d0-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="049d0-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="049d0-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="049d0-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="049d0-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="049d0-121">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="049d0-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="049d0-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="049d0-122">E_FAIL</span></span>|<span data-ttu-id="049d0-123">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="049d0-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="049d0-124">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="049d0-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="049d0-125">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="049d0-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="049d0-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="049d0-126">E_INVALIDARG</span></span>|<span data-ttu-id="049d0-127">策略操作不能设置为指定的操作，或为操作指定了无效策略操作。</span><span class="sxs-lookup"><span data-stu-id="049d0-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="049d0-128">备注</span><span class="sxs-lookup"><span data-stu-id="049d0-128">Remarks</span></span>  
 <span data-ttu-id="049d0-129">默认情况下，CLR 在它无法分配某个资源例如内存时引发异常。</span><span class="sxs-lookup"><span data-stu-id="049d0-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="049d0-130">`SetActionOnFailure` 允许主机通过指定要在失败时执行的策略操作重写此行为。</span><span class="sxs-lookup"><span data-stu-id="049d0-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="049d0-131">下表显示的组合[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)和[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)支持的值。</span><span class="sxs-lookup"><span data-stu-id="049d0-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="049d0-132">(中省略 FAIL_ 前缀[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值。)</span><span class="sxs-lookup"><span data-stu-id="049d0-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="049d0-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="049d0-133">NonCriticalResource</span></span>|<span data-ttu-id="049d0-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="049d0-134">CriticalResource</span></span>|<span data-ttu-id="049d0-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="049d0-135">FatalRuntime</span></span>|<span data-ttu-id="049d0-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="049d0-136">OrphanedLock</span></span>|<span data-ttu-id="049d0-137">堆栈溢出</span><span class="sxs-lookup"><span data-stu-id="049d0-137">StackOverflow</span></span>|<span data-ttu-id="049d0-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="049d0-138">AccessViolation</span></span>|<span data-ttu-id="049d0-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="049d0-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="049d0-140">X</span><span class="sxs-lookup"><span data-stu-id="049d0-140">X</span></span>|<span data-ttu-id="049d0-141">X</span><span class="sxs-lookup"><span data-stu-id="049d0-141">X</span></span>||||<span data-ttu-id="049d0-142">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-142">N/A</span></span>||  
|<span data-ttu-id="049d0-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="049d0-143">eThrowException</span></span>|<span data-ttu-id="049d0-144">X</span><span class="sxs-lookup"><span data-stu-id="049d0-144">X</span></span>|<span data-ttu-id="049d0-145">X</span><span class="sxs-lookup"><span data-stu-id="049d0-145">X</span></span>||||<span data-ttu-id="049d0-146">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="049d0-147">X</span><span class="sxs-lookup"><span data-stu-id="049d0-147">X</span></span>|<span data-ttu-id="049d0-148">X</span><span class="sxs-lookup"><span data-stu-id="049d0-148">X</span></span>||||<span data-ttu-id="049d0-149">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-149">N/A</span></span>|<span data-ttu-id="049d0-150">X</span><span class="sxs-lookup"><span data-stu-id="049d0-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="049d0-151">X</span><span class="sxs-lookup"><span data-stu-id="049d0-151">X</span></span>|<span data-ttu-id="049d0-152">X</span><span class="sxs-lookup"><span data-stu-id="049d0-152">X</span></span>||||<span data-ttu-id="049d0-153">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-153">N/A</span></span>|<span data-ttu-id="049d0-154">X</span><span class="sxs-lookup"><span data-stu-id="049d0-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="049d0-155">X</span><span class="sxs-lookup"><span data-stu-id="049d0-155">X</span></span>|<span data-ttu-id="049d0-156">X</span><span class="sxs-lookup"><span data-stu-id="049d0-156">X</span></span>||<span data-ttu-id="049d0-157">X</span><span class="sxs-lookup"><span data-stu-id="049d0-157">X</span></span>||<span data-ttu-id="049d0-158">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-158">N/A</span></span>|<span data-ttu-id="049d0-159">X</span><span class="sxs-lookup"><span data-stu-id="049d0-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="049d0-160">X</span><span class="sxs-lookup"><span data-stu-id="049d0-160">X</span></span>|<span data-ttu-id="049d0-161">X</span><span class="sxs-lookup"><span data-stu-id="049d0-161">X</span></span>||<span data-ttu-id="049d0-162">X</span><span class="sxs-lookup"><span data-stu-id="049d0-162">X</span></span>|<span data-ttu-id="049d0-163">X</span><span class="sxs-lookup"><span data-stu-id="049d0-163">X</span></span>|<span data-ttu-id="049d0-164">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-164">N/A</span></span>|<span data-ttu-id="049d0-165">X</span><span class="sxs-lookup"><span data-stu-id="049d0-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="049d0-166">X</span><span class="sxs-lookup"><span data-stu-id="049d0-166">X</span></span>|<span data-ttu-id="049d0-167">X</span><span class="sxs-lookup"><span data-stu-id="049d0-167">X</span></span>||<span data-ttu-id="049d0-168">X</span><span class="sxs-lookup"><span data-stu-id="049d0-168">X</span></span>|<span data-ttu-id="049d0-169">X</span><span class="sxs-lookup"><span data-stu-id="049d0-169">X</span></span>|<span data-ttu-id="049d0-170">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-170">N/A</span></span>|<span data-ttu-id="049d0-171">X</span><span class="sxs-lookup"><span data-stu-id="049d0-171">X</span></span>|  
|<span data-ttu-id="049d0-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="049d0-172">eFastExitProcess</span></span>|<span data-ttu-id="049d0-173">X</span><span class="sxs-lookup"><span data-stu-id="049d0-173">X</span></span>|<span data-ttu-id="049d0-174">X</span><span class="sxs-lookup"><span data-stu-id="049d0-174">X</span></span>||<span data-ttu-id="049d0-175">X</span><span class="sxs-lookup"><span data-stu-id="049d0-175">X</span></span>|<span data-ttu-id="049d0-176">X</span><span class="sxs-lookup"><span data-stu-id="049d0-176">X</span></span>|<span data-ttu-id="049d0-177">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="049d0-178">X</span><span class="sxs-lookup"><span data-stu-id="049d0-178">X</span></span>|<span data-ttu-id="049d0-179">X</span><span class="sxs-lookup"><span data-stu-id="049d0-179">X</span></span>|<span data-ttu-id="049d0-180">X</span><span class="sxs-lookup"><span data-stu-id="049d0-180">X</span></span>|<span data-ttu-id="049d0-181">X</span><span class="sxs-lookup"><span data-stu-id="049d0-181">X</span></span>|<span data-ttu-id="049d0-182">X</span><span class="sxs-lookup"><span data-stu-id="049d0-182">X</span></span>|<span data-ttu-id="049d0-183">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="049d0-184">X</span><span class="sxs-lookup"><span data-stu-id="049d0-184">X</span></span>|<span data-ttu-id="049d0-185">X</span><span class="sxs-lookup"><span data-stu-id="049d0-185">X</span></span>|<span data-ttu-id="049d0-186">X</span><span class="sxs-lookup"><span data-stu-id="049d0-186">X</span></span>|<span data-ttu-id="049d0-187">X</span><span class="sxs-lookup"><span data-stu-id="049d0-187">X</span></span>|<span data-ttu-id="049d0-188">X</span><span class="sxs-lookup"><span data-stu-id="049d0-188">X</span></span>|<span data-ttu-id="049d0-189">不可用</span><span class="sxs-lookup"><span data-stu-id="049d0-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="049d0-190">要求</span><span class="sxs-lookup"><span data-stu-id="049d0-190">Requirements</span></span>  
 <span data-ttu-id="049d0-191">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="049d0-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="049d0-192">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="049d0-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="049d0-193">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="049d0-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="049d0-194">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="049d0-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="049d0-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="049d0-195">See Also</span></span>  
 [<span data-ttu-id="049d0-196">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="049d0-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="049d0-197">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="049d0-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="049d0-198">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="049d0-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="049d0-199">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="049d0-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
