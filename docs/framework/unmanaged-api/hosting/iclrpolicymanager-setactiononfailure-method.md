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
ms.openlocfilehash: fb2ecc80f272a3fc9b63b20c5956e7a28f117784
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703472"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="1431f-102">ICLRPolicyManager::SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="1431f-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="1431f-103">指定发生指定的故障时公共语言运行时（CLR）应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="1431f-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1431f-104">语法</span><span class="sxs-lookup"><span data-stu-id="1431f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1431f-105">参数</span><span class="sxs-lookup"><span data-stu-id="1431f-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="1431f-106">中[EClrFailure](eclrfailure-enumeration.md)值之一，指示要采取措施的故障类型。</span><span class="sxs-lookup"><span data-stu-id="1431f-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="1431f-107">中[EPolicyAction](epolicyaction-enumeration.md)值之一，指示发生失败时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="1431f-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="1431f-108">有关支持的值的列表，请参阅 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="1431f-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1431f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1431f-109">Return Value</span></span>  
  
|<span data-ttu-id="1431f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1431f-110">HRESULT</span></span>|<span data-ttu-id="1431f-111">说明</span><span class="sxs-lookup"><span data-stu-id="1431f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1431f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1431f-112">S_OK</span></span>|<span data-ttu-id="1431f-113">`SetActionOnFailure`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1431f-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="1431f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1431f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1431f-115">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1431f-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1431f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1431f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1431f-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="1431f-117">The call timed out.</span></span>|  
|<span data-ttu-id="1431f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1431f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1431f-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1431f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1431f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1431f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1431f-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="1431f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1431f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1431f-122">E_FAIL</span></span>|<span data-ttu-id="1431f-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1431f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1431f-124">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="1431f-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1431f-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1431f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1431f-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1431f-126">E_INVALIDARG</span></span>|<span data-ttu-id="1431f-127">无法为指定的操作设置策略操作，或者为该操作指定了无效的策略操作。</span><span class="sxs-lookup"><span data-stu-id="1431f-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1431f-128">备注</span><span class="sxs-lookup"><span data-stu-id="1431f-128">Remarks</span></span>  
 <span data-ttu-id="1431f-129">默认情况下，CLR 在无法分配内存等资源时引发异常。</span><span class="sxs-lookup"><span data-stu-id="1431f-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="1431f-130">`SetActionOnFailure`允许主机通过指定在失败时要执行的策略操作来重写此行为。</span><span class="sxs-lookup"><span data-stu-id="1431f-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="1431f-131">下表显示了支持的[EClrFailure](eclrfailure-enumeration.md)和[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="1431f-131">The following table shows the combinations of [EClrFailure](eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="1431f-132">（ [EClrFailure](eclrfailure-enumeration.md)值中省略了 FAIL_ 前缀。）</span><span class="sxs-lookup"><span data-stu-id="1431f-132">(The FAIL_ prefix is omitted from [EClrFailure](eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="1431f-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="1431f-133">NonCriticalResource</span></span>|<span data-ttu-id="1431f-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="1431f-134">CriticalResource</span></span>|<span data-ttu-id="1431f-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="1431f-135">FatalRuntime</span></span>|<span data-ttu-id="1431f-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="1431f-136">OrphanedLock</span></span>|<span data-ttu-id="1431f-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="1431f-137">StackOverflow</span></span>|<span data-ttu-id="1431f-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="1431f-138">AccessViolation</span></span>|<span data-ttu-id="1431f-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="1431f-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="1431f-140">X</span><span class="sxs-lookup"><span data-stu-id="1431f-140">X</span></span>|<span data-ttu-id="1431f-141">X</span><span class="sxs-lookup"><span data-stu-id="1431f-141">X</span></span>||||<span data-ttu-id="1431f-142">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-142">N/A</span></span>||  
|<span data-ttu-id="1431f-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="1431f-143">eThrowException</span></span>|<span data-ttu-id="1431f-144">X</span><span class="sxs-lookup"><span data-stu-id="1431f-144">X</span></span>|<span data-ttu-id="1431f-145">X</span><span class="sxs-lookup"><span data-stu-id="1431f-145">X</span></span>||||<span data-ttu-id="1431f-146">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="1431f-147">X</span><span class="sxs-lookup"><span data-stu-id="1431f-147">X</span></span>|<span data-ttu-id="1431f-148">X</span><span class="sxs-lookup"><span data-stu-id="1431f-148">X</span></span>||||<span data-ttu-id="1431f-149">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-149">N/A</span></span>|<span data-ttu-id="1431f-150">X</span><span class="sxs-lookup"><span data-stu-id="1431f-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="1431f-151">X</span><span class="sxs-lookup"><span data-stu-id="1431f-151">X</span></span>|<span data-ttu-id="1431f-152">X</span><span class="sxs-lookup"><span data-stu-id="1431f-152">X</span></span>||||<span data-ttu-id="1431f-153">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-153">N/A</span></span>|<span data-ttu-id="1431f-154">X</span><span class="sxs-lookup"><span data-stu-id="1431f-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="1431f-155">X</span><span class="sxs-lookup"><span data-stu-id="1431f-155">X</span></span>|<span data-ttu-id="1431f-156">X</span><span class="sxs-lookup"><span data-stu-id="1431f-156">X</span></span>||<span data-ttu-id="1431f-157">X</span><span class="sxs-lookup"><span data-stu-id="1431f-157">X</span></span>||<span data-ttu-id="1431f-158">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-158">N/A</span></span>|<span data-ttu-id="1431f-159">X</span><span class="sxs-lookup"><span data-stu-id="1431f-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="1431f-160">X</span><span class="sxs-lookup"><span data-stu-id="1431f-160">X</span></span>|<span data-ttu-id="1431f-161">X</span><span class="sxs-lookup"><span data-stu-id="1431f-161">X</span></span>||<span data-ttu-id="1431f-162">X</span><span class="sxs-lookup"><span data-stu-id="1431f-162">X</span></span>|<span data-ttu-id="1431f-163">X</span><span class="sxs-lookup"><span data-stu-id="1431f-163">X</span></span>|<span data-ttu-id="1431f-164">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-164">N/A</span></span>|<span data-ttu-id="1431f-165">X</span><span class="sxs-lookup"><span data-stu-id="1431f-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="1431f-166">X</span><span class="sxs-lookup"><span data-stu-id="1431f-166">X</span></span>|<span data-ttu-id="1431f-167">X</span><span class="sxs-lookup"><span data-stu-id="1431f-167">X</span></span>||<span data-ttu-id="1431f-168">X</span><span class="sxs-lookup"><span data-stu-id="1431f-168">X</span></span>|<span data-ttu-id="1431f-169">X</span><span class="sxs-lookup"><span data-stu-id="1431f-169">X</span></span>|<span data-ttu-id="1431f-170">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-170">N/A</span></span>|<span data-ttu-id="1431f-171">X</span><span class="sxs-lookup"><span data-stu-id="1431f-171">X</span></span>|  
|<span data-ttu-id="1431f-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="1431f-172">eFastExitProcess</span></span>|<span data-ttu-id="1431f-173">X</span><span class="sxs-lookup"><span data-stu-id="1431f-173">X</span></span>|<span data-ttu-id="1431f-174">X</span><span class="sxs-lookup"><span data-stu-id="1431f-174">X</span></span>||<span data-ttu-id="1431f-175">X</span><span class="sxs-lookup"><span data-stu-id="1431f-175">X</span></span>|<span data-ttu-id="1431f-176">X</span><span class="sxs-lookup"><span data-stu-id="1431f-176">X</span></span>|<span data-ttu-id="1431f-177">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="1431f-178">X</span><span class="sxs-lookup"><span data-stu-id="1431f-178">X</span></span>|<span data-ttu-id="1431f-179">X</span><span class="sxs-lookup"><span data-stu-id="1431f-179">X</span></span>|<span data-ttu-id="1431f-180">X</span><span class="sxs-lookup"><span data-stu-id="1431f-180">X</span></span>|<span data-ttu-id="1431f-181">X</span><span class="sxs-lookup"><span data-stu-id="1431f-181">X</span></span>|<span data-ttu-id="1431f-182">X</span><span class="sxs-lookup"><span data-stu-id="1431f-182">X</span></span>|<span data-ttu-id="1431f-183">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="1431f-184">X</span><span class="sxs-lookup"><span data-stu-id="1431f-184">X</span></span>|<span data-ttu-id="1431f-185">X</span><span class="sxs-lookup"><span data-stu-id="1431f-185">X</span></span>|<span data-ttu-id="1431f-186">X</span><span class="sxs-lookup"><span data-stu-id="1431f-186">X</span></span>|<span data-ttu-id="1431f-187">X</span><span class="sxs-lookup"><span data-stu-id="1431f-187">X</span></span>|<span data-ttu-id="1431f-188">X</span><span class="sxs-lookup"><span data-stu-id="1431f-188">X</span></span>|<span data-ttu-id="1431f-189">空值</span><span class="sxs-lookup"><span data-stu-id="1431f-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="1431f-190">要求</span><span class="sxs-lookup"><span data-stu-id="1431f-190">Requirements</span></span>  
 <span data-ttu-id="1431f-191">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1431f-191">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1431f-192">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1431f-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1431f-193">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1431f-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1431f-194">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1431f-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1431f-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1431f-195">See also</span></span>

- [<span data-ttu-id="1431f-196">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="1431f-196">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="1431f-197">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="1431f-197">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="1431f-198">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="1431f-198">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="1431f-199">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="1431f-199">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
