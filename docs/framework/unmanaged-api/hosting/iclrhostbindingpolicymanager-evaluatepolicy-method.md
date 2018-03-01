---
title: "ICLRHostBindingPolicyManager::EvaluatePolicy 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 14f4db56529fbbb08f8f3d9adde0d4dc7a8ce045
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="1cbfe-102">ICLRHostBindingPolicyManager::EvaluatePolicy 方法</span><span class="sxs-lookup"><span data-stu-id="1cbfe-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="1cbfe-103">代表主机的计算结果绑定策略。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cbfe-104">语法</span><span class="sxs-lookup"><span data-stu-id="1cbfe-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="1cbfe-105">参数</span><span class="sxs-lookup"><span data-stu-id="1cbfe-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="1cbfe-106">[in]对策略评估前的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="1cbfe-107">[in]指向包含策略数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="1cbfe-108">[in]大小`pbApplicationPolicy`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="1cbfe-109">[out]对新的策略数据的计算后的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="1cbfe-110">[在中，out]指向新的策略数据的计算后的程序集标识引用缓冲区大小的指针。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="1cbfe-111">[out]逻辑或组合的指针[EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)值，指示已应用哪些策略。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cbfe-112">返回值</span><span class="sxs-lookup"><span data-stu-id="1cbfe-112">Return Value</span></span>  
  
|<span data-ttu-id="1cbfe-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1cbfe-113">HRESULT</span></span>|<span data-ttu-id="1cbfe-114">描述</span><span class="sxs-lookup"><span data-stu-id="1cbfe-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1cbfe-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="1cbfe-115">S_OK</span></span>|<span data-ttu-id="1cbfe-116">计算已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="1cbfe-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1cbfe-117">E_INVALIDARG</span></span>|<span data-ttu-id="1cbfe-118">请`pwzReferenceIdentity`或`pbApplicationPolicy`为空引用。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="1cbfe-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="1cbfe-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="1cbfe-120">`cbAppPolicySize`对于太小。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="1cbfe-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1cbfe-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1cbfe-122">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1cbfe-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1cbfe-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1cbfe-124">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-124">The call timed out.</span></span>|  
|<span data-ttu-id="1cbfe-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1cbfe-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1cbfe-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1cbfe-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1cbfe-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1cbfe-128">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1cbfe-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1cbfe-129">E_FAIL</span></span>|<span data-ttu-id="1cbfe-130">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1cbfe-131">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1cbfe-132">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cbfe-133">备注</span><span class="sxs-lookup"><span data-stu-id="1cbfe-133">Remarks</span></span>  
 <span data-ttu-id="1cbfe-134">`EvaluatePolicy`方法允许宿主影响绑定策略，以维持特定于宿主的程序集版本控制要求。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="1cbfe-135">策略引擎本身仍保留在 CLR 内。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cbfe-136">惠?</span><span class="sxs-lookup"><span data-stu-id="1cbfe-136">Requirements</span></span>  
 <span data-ttu-id="1cbfe-137">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1cbfe-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cbfe-138">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1cbfe-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cbfe-139">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1cbfe-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cbfe-140">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cbfe-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cbfe-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cbfe-141">See Also</span></span>  
 [<span data-ttu-id="1cbfe-142">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="1cbfe-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
