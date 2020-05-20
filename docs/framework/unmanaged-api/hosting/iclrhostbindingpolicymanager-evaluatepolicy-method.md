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
ms.openlocfilehash: f72a66354bfc907dab7ebc24de515bdfb20ddfb2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703597"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="9f682-102">ICLRHostBindingPolicyManager::EvaluatePolicy 方法</span><span class="sxs-lookup"><span data-stu-id="9f682-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="9f682-103">代表主机计算绑定策略。</span><span class="sxs-lookup"><span data-stu-id="9f682-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f682-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f682-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9f682-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f682-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="9f682-106">中在策略计算之前对程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9f682-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="9f682-107">中指向包含策略数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="9f682-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="9f682-108">中缓冲区的大小 `pbApplicationPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="9f682-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="9f682-109">弄对新策略数据进行计算后对程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9f682-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="9f682-110">[in，out]一个指针，指向对新策略数据进行计算后的程序集标识引用缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="9f682-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="9f682-111">弄指向[EBindPolicyLevels](ebindpolicylevels-enumeration.md)值的逻辑或组合的指针，指示已应用的策略。</span><span class="sxs-lookup"><span data-stu-id="9f682-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f682-112">返回值</span><span class="sxs-lookup"><span data-stu-id="9f682-112">Return Value</span></span>  
  
|<span data-ttu-id="9f682-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f682-113">HRESULT</span></span>|<span data-ttu-id="9f682-114">说明</span><span class="sxs-lookup"><span data-stu-id="9f682-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f682-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f682-115">S_OK</span></span>|<span data-ttu-id="9f682-116">评估已成功完成。</span><span class="sxs-lookup"><span data-stu-id="9f682-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="9f682-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9f682-117">E_INVALIDARG</span></span>|<span data-ttu-id="9f682-118">`pwzReferenceIdentity`或 `pbApplicationPolicy` 为空引用。</span><span class="sxs-lookup"><span data-stu-id="9f682-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="9f682-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9f682-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9f682-120">`cbAppPolicySize` 太小。</span><span class="sxs-lookup"><span data-stu-id="9f682-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="9f682-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9f682-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9f682-122">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9f682-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9f682-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9f682-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9f682-124">调用超时。</span><span class="sxs-lookup"><span data-stu-id="9f682-124">The call timed out.</span></span>|  
|<span data-ttu-id="9f682-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9f682-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9f682-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9f682-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9f682-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9f682-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9f682-128">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="9f682-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9f682-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9f682-129">E_FAIL</span></span>|<span data-ttu-id="9f682-130">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9f682-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9f682-131">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9f682-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9f682-132">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9f682-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f682-133">备注</span><span class="sxs-lookup"><span data-stu-id="9f682-133">Remarks</span></span>  
 <span data-ttu-id="9f682-134">此 `EvaluatePolicy` 方法允许主机影响绑定策略，以维护特定于主机的程序集版本要求。</span><span class="sxs-lookup"><span data-stu-id="9f682-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="9f682-135">策略引擎本身仍保留在 CLR 内。</span><span class="sxs-lookup"><span data-stu-id="9f682-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f682-136">要求</span><span class="sxs-lookup"><span data-stu-id="9f682-136">Requirements</span></span>  
 <span data-ttu-id="9f682-137">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f682-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f682-138">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9f682-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f682-139">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9f682-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f682-140">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f682-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f682-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f682-141">See also</span></span>

- [<span data-ttu-id="9f682-142">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="9f682-142">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
