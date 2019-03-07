---
title: ICLRHostBindingPolicyManager::EvaluatePolicy 方法
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3310f584475a4d6a6f0e3e790db13875faf60cf2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466682"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="11a54-102">ICLRHostBindingPolicyManager::EvaluatePolicy 方法</span><span class="sxs-lookup"><span data-stu-id="11a54-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="11a54-103">代表主机的计算结果绑定策略。</span><span class="sxs-lookup"><span data-stu-id="11a54-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a54-104">语法</span><span class="sxs-lookup"><span data-stu-id="11a54-104">Syntax</span></span>  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11a54-105">参数</span><span class="sxs-lookup"><span data-stu-id="11a54-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="11a54-106">[in]对策略评估前的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="11a54-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="11a54-107">[in]指向包含策略数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="11a54-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="11a54-108">[in]大小`pbApplicationPolicy`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="11a54-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="11a54-109">[out]对新的策略数据的计算后的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="11a54-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="11a54-110">[in、 out]一个指向新的策略数据的计算后的程序集标识引用缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="11a54-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="11a54-111">[out]逻辑或组合的指针[EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)值，指示已应用哪些策略。</span><span class="sxs-lookup"><span data-stu-id="11a54-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11a54-112">返回值</span><span class="sxs-lookup"><span data-stu-id="11a54-112">Return Value</span></span>  
  
|<span data-ttu-id="11a54-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11a54-113">HRESULT</span></span>|<span data-ttu-id="11a54-114">描述</span><span class="sxs-lookup"><span data-stu-id="11a54-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11a54-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="11a54-115">S_OK</span></span>|<span data-ttu-id="11a54-116">已成功完成计算。</span><span class="sxs-lookup"><span data-stu-id="11a54-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="11a54-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="11a54-117">E_INVALIDARG</span></span>|<span data-ttu-id="11a54-118">要么`pwzReferenceIdentity`或`pbApplicationPolicy`为 null 引用。</span><span class="sxs-lookup"><span data-stu-id="11a54-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="11a54-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="11a54-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="11a54-120">`cbAppPolicySize` 是太小。</span><span class="sxs-lookup"><span data-stu-id="11a54-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="11a54-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11a54-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11a54-122">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="11a54-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11a54-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11a54-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11a54-124">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="11a54-124">The call timed out.</span></span>|  
|<span data-ttu-id="11a54-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11a54-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11a54-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="11a54-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11a54-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11a54-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11a54-128">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="11a54-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11a54-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11a54-129">E_FAIL</span></span>|<span data-ttu-id="11a54-130">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="11a54-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="11a54-131">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="11a54-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11a54-132">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="11a54-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11a54-133">备注</span><span class="sxs-lookup"><span data-stu-id="11a54-133">Remarks</span></span>  
 <span data-ttu-id="11a54-134">`EvaluatePolicy`方法使主机可影响绑定策略来维护特定于宿主的程序集版本控制要求。</span><span class="sxs-lookup"><span data-stu-id="11a54-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="11a54-135">策略引擎本身仍保留在 CLR 内。</span><span class="sxs-lookup"><span data-stu-id="11a54-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a54-136">要求</span><span class="sxs-lookup"><span data-stu-id="11a54-136">Requirements</span></span>  
 <span data-ttu-id="11a54-137">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11a54-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a54-138">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11a54-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11a54-139">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="11a54-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11a54-140">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a54-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a54-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="11a54-141">See also</span></span>
- [<span data-ttu-id="11a54-142">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="11a54-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
