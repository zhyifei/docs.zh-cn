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
ms.openlocfilehash: 143052febe136e969987c35bc06f6c3b3356aedf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140781"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="6d963-102">ICLRPolicyManager::SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="6d963-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="6d963-103">指定发生指定的故障时公共语言运行时（CLR）应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="6d963-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d963-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d963-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d963-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d963-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="6d963-106">中[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值之一，指示要采取措施的故障类型。</span><span class="sxs-lookup"><span data-stu-id="6d963-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="6d963-107">中[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值之一，指示发生失败时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="6d963-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="6d963-108">有关支持的值的列表，请参阅 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="6d963-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d963-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6d963-109">Return Value</span></span>  
  
|<span data-ttu-id="6d963-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d963-110">HRESULT</span></span>|<span data-ttu-id="6d963-111">描述</span><span class="sxs-lookup"><span data-stu-id="6d963-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d963-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d963-112">S_OK</span></span>|<span data-ttu-id="6d963-113">`SetActionOnFailure` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="6d963-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="6d963-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d963-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d963-115">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="6d963-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d963-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d963-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d963-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="6d963-117">The call timed out.</span></span>|  
|<span data-ttu-id="6d963-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d963-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d963-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="6d963-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d963-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d963-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d963-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="6d963-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d963-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d963-122">E_FAIL</span></span>|<span data-ttu-id="6d963-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="6d963-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d963-124">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="6d963-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d963-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="6d963-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6d963-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6d963-126">E_INVALIDARG</span></span>|<span data-ttu-id="6d963-127">无法为指定的操作设置策略操作，或者为该操作指定了无效的策略操作。</span><span class="sxs-lookup"><span data-stu-id="6d963-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d963-128">备注</span><span class="sxs-lookup"><span data-stu-id="6d963-128">Remarks</span></span>  
 <span data-ttu-id="6d963-129">默认情况下，CLR 在无法分配内存等资源时引发异常。</span><span class="sxs-lookup"><span data-stu-id="6d963-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="6d963-130">`SetActionOnFailure` 允许主机通过指定在失败时要执行的策略操作来重写此行为。</span><span class="sxs-lookup"><span data-stu-id="6d963-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="6d963-131">下表显示了支持的[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)和[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="6d963-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="6d963-132">（ [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值中省略了 FAIL_ 前缀。）</span><span class="sxs-lookup"><span data-stu-id="6d963-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="6d963-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="6d963-133">NonCriticalResource</span></span>|<span data-ttu-id="6d963-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="6d963-134">CriticalResource</span></span>|<span data-ttu-id="6d963-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="6d963-135">FatalRuntime</span></span>|<span data-ttu-id="6d963-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="6d963-136">OrphanedLock</span></span>|<span data-ttu-id="6d963-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="6d963-137">StackOverflow</span></span>|<span data-ttu-id="6d963-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="6d963-138">AccessViolation</span></span>|<span data-ttu-id="6d963-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="6d963-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="6d963-140">x</span><span class="sxs-lookup"><span data-stu-id="6d963-140">X</span></span>|<span data-ttu-id="6d963-141">x</span><span class="sxs-lookup"><span data-stu-id="6d963-141">X</span></span>||||<span data-ttu-id="6d963-142">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-142">N/A</span></span>||  
|<span data-ttu-id="6d963-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="6d963-143">eThrowException</span></span>|<span data-ttu-id="6d963-144">x</span><span class="sxs-lookup"><span data-stu-id="6d963-144">X</span></span>|<span data-ttu-id="6d963-145">x</span><span class="sxs-lookup"><span data-stu-id="6d963-145">X</span></span>||||<span data-ttu-id="6d963-146">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="6d963-147">x</span><span class="sxs-lookup"><span data-stu-id="6d963-147">X</span></span>|<span data-ttu-id="6d963-148">x</span><span class="sxs-lookup"><span data-stu-id="6d963-148">X</span></span>||||<span data-ttu-id="6d963-149">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-149">N/A</span></span>|<span data-ttu-id="6d963-150">x</span><span class="sxs-lookup"><span data-stu-id="6d963-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="6d963-151">x</span><span class="sxs-lookup"><span data-stu-id="6d963-151">X</span></span>|<span data-ttu-id="6d963-152">x</span><span class="sxs-lookup"><span data-stu-id="6d963-152">X</span></span>||||<span data-ttu-id="6d963-153">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-153">N/A</span></span>|<span data-ttu-id="6d963-154">x</span><span class="sxs-lookup"><span data-stu-id="6d963-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="6d963-155">x</span><span class="sxs-lookup"><span data-stu-id="6d963-155">X</span></span>|<span data-ttu-id="6d963-156">x</span><span class="sxs-lookup"><span data-stu-id="6d963-156">X</span></span>||<span data-ttu-id="6d963-157">x</span><span class="sxs-lookup"><span data-stu-id="6d963-157">X</span></span>||<span data-ttu-id="6d963-158">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-158">N/A</span></span>|<span data-ttu-id="6d963-159">x</span><span class="sxs-lookup"><span data-stu-id="6d963-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="6d963-160">x</span><span class="sxs-lookup"><span data-stu-id="6d963-160">X</span></span>|<span data-ttu-id="6d963-161">x</span><span class="sxs-lookup"><span data-stu-id="6d963-161">X</span></span>||<span data-ttu-id="6d963-162">x</span><span class="sxs-lookup"><span data-stu-id="6d963-162">X</span></span>|<span data-ttu-id="6d963-163">x</span><span class="sxs-lookup"><span data-stu-id="6d963-163">X</span></span>|<span data-ttu-id="6d963-164">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-164">N/A</span></span>|<span data-ttu-id="6d963-165">x</span><span class="sxs-lookup"><span data-stu-id="6d963-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="6d963-166">x</span><span class="sxs-lookup"><span data-stu-id="6d963-166">X</span></span>|<span data-ttu-id="6d963-167">x</span><span class="sxs-lookup"><span data-stu-id="6d963-167">X</span></span>||<span data-ttu-id="6d963-168">x</span><span class="sxs-lookup"><span data-stu-id="6d963-168">X</span></span>|<span data-ttu-id="6d963-169">x</span><span class="sxs-lookup"><span data-stu-id="6d963-169">X</span></span>|<span data-ttu-id="6d963-170">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-170">N/A</span></span>|<span data-ttu-id="6d963-171">x</span><span class="sxs-lookup"><span data-stu-id="6d963-171">X</span></span>|  
|<span data-ttu-id="6d963-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="6d963-172">eFastExitProcess</span></span>|<span data-ttu-id="6d963-173">x</span><span class="sxs-lookup"><span data-stu-id="6d963-173">X</span></span>|<span data-ttu-id="6d963-174">x</span><span class="sxs-lookup"><span data-stu-id="6d963-174">X</span></span>||<span data-ttu-id="6d963-175">x</span><span class="sxs-lookup"><span data-stu-id="6d963-175">X</span></span>|<span data-ttu-id="6d963-176">x</span><span class="sxs-lookup"><span data-stu-id="6d963-176">X</span></span>|<span data-ttu-id="6d963-177">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="6d963-178">x</span><span class="sxs-lookup"><span data-stu-id="6d963-178">X</span></span>|<span data-ttu-id="6d963-179">x</span><span class="sxs-lookup"><span data-stu-id="6d963-179">X</span></span>|<span data-ttu-id="6d963-180">x</span><span class="sxs-lookup"><span data-stu-id="6d963-180">X</span></span>|<span data-ttu-id="6d963-181">x</span><span class="sxs-lookup"><span data-stu-id="6d963-181">X</span></span>|<span data-ttu-id="6d963-182">x</span><span class="sxs-lookup"><span data-stu-id="6d963-182">X</span></span>|<span data-ttu-id="6d963-183">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="6d963-184">x</span><span class="sxs-lookup"><span data-stu-id="6d963-184">X</span></span>|<span data-ttu-id="6d963-185">x</span><span class="sxs-lookup"><span data-stu-id="6d963-185">X</span></span>|<span data-ttu-id="6d963-186">x</span><span class="sxs-lookup"><span data-stu-id="6d963-186">X</span></span>|<span data-ttu-id="6d963-187">x</span><span class="sxs-lookup"><span data-stu-id="6d963-187">X</span></span>|<span data-ttu-id="6d963-188">x</span><span class="sxs-lookup"><span data-stu-id="6d963-188">X</span></span>|<span data-ttu-id="6d963-189">不可用</span><span class="sxs-lookup"><span data-stu-id="6d963-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="6d963-190">要求</span><span class="sxs-lookup"><span data-stu-id="6d963-190">Requirements</span></span>  
 <span data-ttu-id="6d963-191">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d963-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d963-192">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6d963-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d963-193">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6d963-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d963-194">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d963-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d963-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d963-195">See also</span></span>

- [<span data-ttu-id="6d963-196">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="6d963-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="6d963-197">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="6d963-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="6d963-198">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="6d963-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6d963-199">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="6d963-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
