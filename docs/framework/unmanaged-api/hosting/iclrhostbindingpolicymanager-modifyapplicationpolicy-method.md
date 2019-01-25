---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy 方法
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45e0099ea60a338f0ea1ef414f4d2fa1c33c9d70
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726879"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="1f4b1-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="1f4b1-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="1f4b1-103">修改为指定的程序集绑定策略和创建策略的新版本。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f4b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f4b1-104">Syntax</span></span>  
  
```  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f4b1-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f4b1-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="1f4b1-106">[in]要修改的程序集的标识。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="1f4b1-107">[in]修改后的程序集的新标识。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="1f4b1-108">[in]指向包含要修改的程序集绑定策略数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="1f4b1-109">[in]要替换的绑定策略的大小。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="1f4b1-110">[in]逻辑或组合[EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)值，指示重定向的控件。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="1f4b1-111">[out]指向包含新的绑定策略数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="1f4b1-112">[in、 out]一个指向新的绑定策略缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f4b1-113">返回值</span><span class="sxs-lookup"><span data-stu-id="1f4b1-113">Return Value</span></span>  
  
|<span data-ttu-id="1f4b1-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f4b1-114">HRESULT</span></span>|<span data-ttu-id="1f4b1-115">描述</span><span class="sxs-lookup"><span data-stu-id="1f4b1-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f4b1-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f4b1-116">S_OK</span></span>|<span data-ttu-id="1f4b1-117">已成功修改策略。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="1f4b1-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1f4b1-118">E_INVALIDARG</span></span>|<span data-ttu-id="1f4b1-119">`pwzSourceAssemblyIdentity` 或`pwzTargetAssemblyIdentity`是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="1f4b1-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="1f4b1-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="1f4b1-121">`pbNewApplicationPolicy` 是太小。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="1f4b1-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1f4b1-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1f4b1-123">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1f4b1-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1f4b1-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1f4b1-125">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-125">The call timed out.</span></span>|  
|<span data-ttu-id="1f4b1-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1f4b1-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1f4b1-127">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1f4b1-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1f4b1-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1f4b1-129">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1f4b1-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1f4b1-130">E_FAIL</span></span>|<span data-ttu-id="1f4b1-131">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1f4b1-132">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1f4b1-133">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f4b1-134">备注</span><span class="sxs-lookup"><span data-stu-id="1f4b1-134">Remarks</span></span>  
 <span data-ttu-id="1f4b1-135">`ModifyApplicationPolicy`两次调用方法。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="1f4b1-136">第一次调用应提供 null 值的`pbNewApplicationPolicy`参数。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="1f4b1-137">此调用将返回必需的值与`pcbNewAppPolicySize`。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="1f4b1-138">第二次调用应提供此值用于`pcbNewAppPolicySize`，并指向该大小的缓冲区`pbNewApplicationPolicy`。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f4b1-139">要求</span><span class="sxs-lookup"><span data-stu-id="1f4b1-139">Requirements</span></span>  
 <span data-ttu-id="1f4b1-140">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f4b1-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f4b1-141">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1f4b1-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f4b1-142">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1f4b1-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f4b1-143">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f4b1-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f4b1-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f4b1-144">See also</span></span>
- [<span data-ttu-id="1f4b1-145">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="1f4b1-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
