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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117425"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="f65f4-102">ICLRPolicyManager::SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="f65f4-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="f65f4-103">指定公共语言运行时 (CLR) 指定的故障发生时应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="f65f4-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f65f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="f65f4-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f65f4-105">参数</span><span class="sxs-lookup"><span data-stu-id="f65f4-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="f65f4-106">[in]之一[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值，它指示要为其执行操作失败的类型。</span><span class="sxs-lookup"><span data-stu-id="f65f4-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="f65f4-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示出现故障时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f65f4-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="f65f4-108">有关支持的值的列表，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="f65f4-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f65f4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f65f4-109">Return Value</span></span>  
  
|<span data-ttu-id="f65f4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f65f4-110">HRESULT</span></span>|<span data-ttu-id="f65f4-111">描述</span><span class="sxs-lookup"><span data-stu-id="f65f4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f65f4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f65f4-112">S_OK</span></span>|`SetActionOnFailure` <span data-ttu-id="f65f4-113">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f65f4-113">returned successfully.</span></span>|  
|<span data-ttu-id="f65f4-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f65f4-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f65f4-115">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f65f4-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f65f4-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f65f4-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f65f4-117">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="f65f4-117">The call timed out.</span></span>|  
|<span data-ttu-id="f65f4-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f65f4-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f65f4-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f65f4-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f65f4-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f65f4-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f65f4-121">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f65f4-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f65f4-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f65f4-122">E_FAIL</span></span>|<span data-ttu-id="f65f4-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f65f4-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f65f4-124">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="f65f4-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f65f4-125">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f65f4-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f65f4-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f65f4-126">E_INVALIDARG</span></span>|<span data-ttu-id="f65f4-127">策略操作不能设置为指定的操作，或为操作指定了无效的策略操作。</span><span class="sxs-lookup"><span data-stu-id="f65f4-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f65f4-128">备注</span><span class="sxs-lookup"><span data-stu-id="f65f4-128">Remarks</span></span>  
 <span data-ttu-id="f65f4-129">默认情况下，CLR 无法分配内存等资源时引发异常。</span><span class="sxs-lookup"><span data-stu-id="f65f4-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> `SetActionOnFailure` <span data-ttu-id="f65f4-130">允许重写此行为，通过指定要在失败时执行的策略操作主机。</span><span class="sxs-lookup"><span data-stu-id="f65f4-130">allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="f65f4-131">下表显示了的组合[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)并[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)支持的值。</span><span class="sxs-lookup"><span data-stu-id="f65f4-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="f65f4-132">(从省略 FAIL_ 前缀[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值。)</span><span class="sxs-lookup"><span data-stu-id="f65f4-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="f65f4-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="f65f4-133">NonCriticalResource</span></span>|<span data-ttu-id="f65f4-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="f65f4-134">CriticalResource</span></span>|<span data-ttu-id="f65f4-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="f65f4-135">FatalRuntime</span></span>|<span data-ttu-id="f65f4-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="f65f4-136">OrphanedLock</span></span>|<span data-ttu-id="f65f4-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="f65f4-137">StackOverflow</span></span>|<span data-ttu-id="f65f4-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="f65f4-138">AccessViolation</span></span>|<span data-ttu-id="f65f4-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="f65f4-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="f65f4-140">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-140">X</span></span>|<span data-ttu-id="f65f4-141">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-141">X</span></span>||||<span data-ttu-id="f65f4-142">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-142">N/A</span></span>||  
|<span data-ttu-id="f65f4-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="f65f4-143">eThrowException</span></span>|<span data-ttu-id="f65f4-144">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-144">X</span></span>|<span data-ttu-id="f65f4-145">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-145">X</span></span>||||<span data-ttu-id="f65f4-146">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="f65f4-147">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-147">X</span></span>|<span data-ttu-id="f65f4-148">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-148">X</span></span>||||<span data-ttu-id="f65f4-149">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-149">N/A</span></span>|<span data-ttu-id="f65f4-150">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="f65f4-151">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-151">X</span></span>|<span data-ttu-id="f65f4-152">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-152">X</span></span>||||<span data-ttu-id="f65f4-153">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-153">N/A</span></span>|<span data-ttu-id="f65f4-154">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="f65f4-155">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-155">X</span></span>|<span data-ttu-id="f65f4-156">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-156">X</span></span>||<span data-ttu-id="f65f4-157">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-157">X</span></span>||<span data-ttu-id="f65f4-158">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-158">N/A</span></span>|<span data-ttu-id="f65f4-159">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="f65f4-160">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-160">X</span></span>|<span data-ttu-id="f65f4-161">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-161">X</span></span>||<span data-ttu-id="f65f4-162">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-162">X</span></span>|<span data-ttu-id="f65f4-163">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-163">X</span></span>|<span data-ttu-id="f65f4-164">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-164">N/A</span></span>|<span data-ttu-id="f65f4-165">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="f65f4-166">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-166">X</span></span>|<span data-ttu-id="f65f4-167">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-167">X</span></span>||<span data-ttu-id="f65f4-168">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-168">X</span></span>|<span data-ttu-id="f65f4-169">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-169">X</span></span>|<span data-ttu-id="f65f4-170">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-170">N/A</span></span>|<span data-ttu-id="f65f4-171">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-171">X</span></span>|  
|<span data-ttu-id="f65f4-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="f65f4-172">eFastExitProcess</span></span>|<span data-ttu-id="f65f4-173">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-173">X</span></span>|<span data-ttu-id="f65f4-174">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-174">X</span></span>||<span data-ttu-id="f65f4-175">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-175">X</span></span>|<span data-ttu-id="f65f4-176">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-176">X</span></span>|<span data-ttu-id="f65f4-177">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="f65f4-178">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-178">X</span></span>|<span data-ttu-id="f65f4-179">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-179">X</span></span>|<span data-ttu-id="f65f4-180">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-180">X</span></span>|<span data-ttu-id="f65f4-181">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-181">X</span></span>|<span data-ttu-id="f65f4-182">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-182">X</span></span>|<span data-ttu-id="f65f4-183">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="f65f4-184">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-184">X</span></span>|<span data-ttu-id="f65f4-185">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-185">X</span></span>|<span data-ttu-id="f65f4-186">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-186">X</span></span>|<span data-ttu-id="f65f4-187">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-187">X</span></span>|<span data-ttu-id="f65f4-188">X</span><span class="sxs-lookup"><span data-stu-id="f65f4-188">X</span></span>|<span data-ttu-id="f65f4-189">不可用</span><span class="sxs-lookup"><span data-stu-id="f65f4-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="f65f4-190">要求</span><span class="sxs-lookup"><span data-stu-id="f65f4-190">Requirements</span></span>  
 <span data-ttu-id="f65f4-191">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f65f4-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f65f4-192">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f65f4-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f65f4-193">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f65f4-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f65f4-194">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f65f4-194">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f65f4-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="f65f4-195">See also</span></span>

- [<span data-ttu-id="f65f4-196">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="f65f4-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="f65f4-197">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="f65f4-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="f65f4-198">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="f65f4-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="f65f4-199">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="f65f4-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
