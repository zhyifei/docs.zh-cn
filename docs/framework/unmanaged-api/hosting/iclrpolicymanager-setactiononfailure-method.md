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
ms.openlocfilehash: 34d9e1a3747ecf3dffc925d7883599b773dd51f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117425"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="a9486-102">ICLRPolicyManager::SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="a9486-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="a9486-103">指定公共语言运行时 (CLR) 指定的故障发生时应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="a9486-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9486-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9486-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9486-105">参数</span><span class="sxs-lookup"><span data-stu-id="a9486-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="a9486-106">[in]之一[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值，它指示要为其执行操作失败的类型。</span><span class="sxs-lookup"><span data-stu-id="a9486-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="a9486-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示出现故障时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a9486-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="a9486-108">有关支持的值的列表，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="a9486-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9486-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a9486-109">Return Value</span></span>  
  
|<span data-ttu-id="a9486-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9486-110">HRESULT</span></span>|<span data-ttu-id="a9486-111">描述</span><span class="sxs-lookup"><span data-stu-id="a9486-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9486-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9486-112">S_OK</span></span>|<span data-ttu-id="a9486-113">`SetActionOnFailure` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a9486-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="a9486-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9486-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9486-115">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a9486-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9486-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9486-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9486-117">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="a9486-117">The call timed out.</span></span>|  
|<span data-ttu-id="a9486-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9486-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9486-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a9486-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9486-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9486-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9486-121">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="a9486-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9486-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9486-122">E_FAIL</span></span>|<span data-ttu-id="a9486-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a9486-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9486-124">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="a9486-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9486-125">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a9486-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a9486-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a9486-126">E_INVALIDARG</span></span>|<span data-ttu-id="a9486-127">策略操作不能设置为指定的操作，或为操作指定了无效的策略操作。</span><span class="sxs-lookup"><span data-stu-id="a9486-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9486-128">备注</span><span class="sxs-lookup"><span data-stu-id="a9486-128">Remarks</span></span>  
 <span data-ttu-id="a9486-129">默认情况下，CLR 无法分配内存等资源时引发异常。</span><span class="sxs-lookup"><span data-stu-id="a9486-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="a9486-130">`SetActionOnFailure` 允许重写此行为，通过指定要在失败时执行的策略操作主机。</span><span class="sxs-lookup"><span data-stu-id="a9486-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="a9486-131">下表显示了的组合[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)并[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)支持的值。</span><span class="sxs-lookup"><span data-stu-id="a9486-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="a9486-132">(从省略 FAIL_ 前缀[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值。)</span><span class="sxs-lookup"><span data-stu-id="a9486-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="a9486-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="a9486-133">NonCriticalResource</span></span>|<span data-ttu-id="a9486-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="a9486-134">CriticalResource</span></span>|<span data-ttu-id="a9486-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="a9486-135">FatalRuntime</span></span>|<span data-ttu-id="a9486-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="a9486-136">OrphanedLock</span></span>|<span data-ttu-id="a9486-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="a9486-137">StackOverflow</span></span>|<span data-ttu-id="a9486-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="a9486-138">AccessViolation</span></span>|<span data-ttu-id="a9486-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="a9486-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="a9486-140">X</span><span class="sxs-lookup"><span data-stu-id="a9486-140">X</span></span>|<span data-ttu-id="a9486-141">X</span><span class="sxs-lookup"><span data-stu-id="a9486-141">X</span></span>||||<span data-ttu-id="a9486-142">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-142">N/A</span></span>||  
|<span data-ttu-id="a9486-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="a9486-143">eThrowException</span></span>|<span data-ttu-id="a9486-144">X</span><span class="sxs-lookup"><span data-stu-id="a9486-144">X</span></span>|<span data-ttu-id="a9486-145">X</span><span class="sxs-lookup"><span data-stu-id="a9486-145">X</span></span>||||<span data-ttu-id="a9486-146">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="a9486-147">X</span><span class="sxs-lookup"><span data-stu-id="a9486-147">X</span></span>|<span data-ttu-id="a9486-148">X</span><span class="sxs-lookup"><span data-stu-id="a9486-148">X</span></span>||||<span data-ttu-id="a9486-149">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-149">N/A</span></span>|<span data-ttu-id="a9486-150">X</span><span class="sxs-lookup"><span data-stu-id="a9486-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="a9486-151">X</span><span class="sxs-lookup"><span data-stu-id="a9486-151">X</span></span>|<span data-ttu-id="a9486-152">X</span><span class="sxs-lookup"><span data-stu-id="a9486-152">X</span></span>||||<span data-ttu-id="a9486-153">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-153">N/A</span></span>|<span data-ttu-id="a9486-154">X</span><span class="sxs-lookup"><span data-stu-id="a9486-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="a9486-155">X</span><span class="sxs-lookup"><span data-stu-id="a9486-155">X</span></span>|<span data-ttu-id="a9486-156">X</span><span class="sxs-lookup"><span data-stu-id="a9486-156">X</span></span>||<span data-ttu-id="a9486-157">X</span><span class="sxs-lookup"><span data-stu-id="a9486-157">X</span></span>||<span data-ttu-id="a9486-158">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-158">N/A</span></span>|<span data-ttu-id="a9486-159">X</span><span class="sxs-lookup"><span data-stu-id="a9486-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="a9486-160">X</span><span class="sxs-lookup"><span data-stu-id="a9486-160">X</span></span>|<span data-ttu-id="a9486-161">X</span><span class="sxs-lookup"><span data-stu-id="a9486-161">X</span></span>||<span data-ttu-id="a9486-162">X</span><span class="sxs-lookup"><span data-stu-id="a9486-162">X</span></span>|<span data-ttu-id="a9486-163">X</span><span class="sxs-lookup"><span data-stu-id="a9486-163">X</span></span>|<span data-ttu-id="a9486-164">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-164">N/A</span></span>|<span data-ttu-id="a9486-165">X</span><span class="sxs-lookup"><span data-stu-id="a9486-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="a9486-166">X</span><span class="sxs-lookup"><span data-stu-id="a9486-166">X</span></span>|<span data-ttu-id="a9486-167">X</span><span class="sxs-lookup"><span data-stu-id="a9486-167">X</span></span>||<span data-ttu-id="a9486-168">X</span><span class="sxs-lookup"><span data-stu-id="a9486-168">X</span></span>|<span data-ttu-id="a9486-169">X</span><span class="sxs-lookup"><span data-stu-id="a9486-169">X</span></span>|<span data-ttu-id="a9486-170">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-170">N/A</span></span>|<span data-ttu-id="a9486-171">X</span><span class="sxs-lookup"><span data-stu-id="a9486-171">X</span></span>|  
|<span data-ttu-id="a9486-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a9486-172">eFastExitProcess</span></span>|<span data-ttu-id="a9486-173">X</span><span class="sxs-lookup"><span data-stu-id="a9486-173">X</span></span>|<span data-ttu-id="a9486-174">X</span><span class="sxs-lookup"><span data-stu-id="a9486-174">X</span></span>||<span data-ttu-id="a9486-175">X</span><span class="sxs-lookup"><span data-stu-id="a9486-175">X</span></span>|<span data-ttu-id="a9486-176">X</span><span class="sxs-lookup"><span data-stu-id="a9486-176">X</span></span>|<span data-ttu-id="a9486-177">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="a9486-178">X</span><span class="sxs-lookup"><span data-stu-id="a9486-178">X</span></span>|<span data-ttu-id="a9486-179">X</span><span class="sxs-lookup"><span data-stu-id="a9486-179">X</span></span>|<span data-ttu-id="a9486-180">X</span><span class="sxs-lookup"><span data-stu-id="a9486-180">X</span></span>|<span data-ttu-id="a9486-181">X</span><span class="sxs-lookup"><span data-stu-id="a9486-181">X</span></span>|<span data-ttu-id="a9486-182">X</span><span class="sxs-lookup"><span data-stu-id="a9486-182">X</span></span>|<span data-ttu-id="a9486-183">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="a9486-184">X</span><span class="sxs-lookup"><span data-stu-id="a9486-184">X</span></span>|<span data-ttu-id="a9486-185">X</span><span class="sxs-lookup"><span data-stu-id="a9486-185">X</span></span>|<span data-ttu-id="a9486-186">X</span><span class="sxs-lookup"><span data-stu-id="a9486-186">X</span></span>|<span data-ttu-id="a9486-187">X</span><span class="sxs-lookup"><span data-stu-id="a9486-187">X</span></span>|<span data-ttu-id="a9486-188">X</span><span class="sxs-lookup"><span data-stu-id="a9486-188">X</span></span>|<span data-ttu-id="a9486-189">不适用</span><span class="sxs-lookup"><span data-stu-id="a9486-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="a9486-190">要求</span><span class="sxs-lookup"><span data-stu-id="a9486-190">Requirements</span></span>  
 <span data-ttu-id="a9486-191">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9486-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9486-192">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9486-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9486-193">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a9486-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9486-194">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9486-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9486-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9486-195">See also</span></span>

- [<span data-ttu-id="a9486-196">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="a9486-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="a9486-197">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="a9486-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="a9486-198">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="a9486-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a9486-199">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="a9486-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
