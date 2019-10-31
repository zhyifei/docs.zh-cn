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
ms.openlocfilehash: 9600573a0a730cee10247d5644d587e75856cdd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141177"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="9ba71-102">ICLRHostBindingPolicyManager::EvaluatePolicy 方法</span><span class="sxs-lookup"><span data-stu-id="9ba71-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="9ba71-103">代表主机计算绑定策略。</span><span class="sxs-lookup"><span data-stu-id="9ba71-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ba71-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ba71-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ba71-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ba71-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="9ba71-106">中在策略计算之前对程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9ba71-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="9ba71-107">中指向包含策略数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="9ba71-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="9ba71-108">中`pbApplicationPolicy` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="9ba71-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="9ba71-109">弄对新策略数据进行计算后对程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9ba71-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="9ba71-110">[in，out]一个指针，指向对新策略数据进行计算后的程序集标识引用缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="9ba71-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="9ba71-111">弄指向[EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)值的逻辑或组合的指针，指示已应用的策略。</span><span class="sxs-lookup"><span data-stu-id="9ba71-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ba71-112">返回值</span><span class="sxs-lookup"><span data-stu-id="9ba71-112">Return Value</span></span>  
  
|<span data-ttu-id="9ba71-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ba71-113">HRESULT</span></span>|<span data-ttu-id="9ba71-114">描述</span><span class="sxs-lookup"><span data-stu-id="9ba71-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ba71-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ba71-115">S_OK</span></span>|<span data-ttu-id="9ba71-116">评估已成功完成。</span><span class="sxs-lookup"><span data-stu-id="9ba71-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="9ba71-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9ba71-117">E_INVALIDARG</span></span>|<span data-ttu-id="9ba71-118">`pwzReferenceIdentity` 或 `pbApplicationPolicy` 为空引用。</span><span class="sxs-lookup"><span data-stu-id="9ba71-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="9ba71-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9ba71-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9ba71-120">`cbAppPolicySize` 太小。</span><span class="sxs-lookup"><span data-stu-id="9ba71-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="9ba71-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ba71-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ba71-122">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9ba71-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ba71-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ba71-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ba71-124">调用超时。</span><span class="sxs-lookup"><span data-stu-id="9ba71-124">The call timed out.</span></span>|  
|<span data-ttu-id="9ba71-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ba71-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ba71-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9ba71-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ba71-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ba71-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ba71-128">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="9ba71-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ba71-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ba71-129">E_FAIL</span></span>|<span data-ttu-id="9ba71-130">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9ba71-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ba71-131">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9ba71-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ba71-132">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9ba71-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ba71-133">备注</span><span class="sxs-lookup"><span data-stu-id="9ba71-133">Remarks</span></span>  
 <span data-ttu-id="9ba71-134">`EvaluatePolicy` 方法允许宿主影响绑定策略，以维护特定于主机的程序集的版本要求。</span><span class="sxs-lookup"><span data-stu-id="9ba71-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="9ba71-135">策略引擎本身仍保留在 CLR 内。</span><span class="sxs-lookup"><span data-stu-id="9ba71-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ba71-136">要求</span><span class="sxs-lookup"><span data-stu-id="9ba71-136">Requirements</span></span>  
 <span data-ttu-id="9ba71-137">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ba71-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ba71-138">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9ba71-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ba71-139">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9ba71-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ba71-140">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ba71-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba71-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ba71-141">See also</span></span>

- [<span data-ttu-id="9ba71-142">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="9ba71-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
