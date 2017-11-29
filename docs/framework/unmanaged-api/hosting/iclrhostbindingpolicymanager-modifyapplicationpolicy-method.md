---
title: "ICLRHostBindingPolicyManager::ModifyApplicationPolicy 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 51775f52e34f35d8ef9f3a8533363be73e9bd7c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="f8c75-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="f8c75-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="f8c75-103">修改指定的程序集绑定策略，并创建新版本的策略。</span><span class="sxs-lookup"><span data-stu-id="f8c75-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8c75-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8c75-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f8c75-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8c75-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="f8c75-106">[in]要修改的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="f8c75-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="f8c75-107">[in]修改后的程序集的新标识。</span><span class="sxs-lookup"><span data-stu-id="f8c75-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="f8c75-108">[in]指向包含要修改的程序集绑定策略数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="f8c75-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="f8c75-109">[in]要替换的绑定策略的大小。</span><span class="sxs-lookup"><span data-stu-id="f8c75-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="f8c75-110">[in]逻辑或组合[EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)值，表明控制的重定向。</span><span class="sxs-lookup"><span data-stu-id="f8c75-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="f8c75-111">[out]指向包含新的绑定策略数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="f8c75-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="f8c75-112">[在中，out]指向新的绑定策略缓冲区的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="f8c75-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8c75-113">返回值</span><span class="sxs-lookup"><span data-stu-id="f8c75-113">Return Value</span></span>  
  
|<span data-ttu-id="f8c75-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8c75-114">HRESULT</span></span>|<span data-ttu-id="f8c75-115">描述</span><span class="sxs-lookup"><span data-stu-id="f8c75-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8c75-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8c75-116">S_OK</span></span>|<span data-ttu-id="f8c75-117">已成功修改策略。</span><span class="sxs-lookup"><span data-stu-id="f8c75-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="f8c75-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f8c75-118">E_INVALIDARG</span></span>|<span data-ttu-id="f8c75-119">`pwzSourceAssemblyIdentity`或`pwzTargetAssemblyIdentity`是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="f8c75-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="f8c75-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f8c75-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f8c75-121">`pbNewApplicationPolicy`对于太小。</span><span class="sxs-lookup"><span data-stu-id="f8c75-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="f8c75-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f8c75-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f8c75-123">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f8c75-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f8c75-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f8c75-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f8c75-125">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="f8c75-125">The call timed out.</span></span>|  
|<span data-ttu-id="f8c75-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f8c75-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f8c75-127">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f8c75-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f8c75-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f8c75-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f8c75-129">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f8c75-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f8c75-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f8c75-130">E_FAIL</span></span>|<span data-ttu-id="f8c75-131">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f8c75-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f8c75-132">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="f8c75-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f8c75-133">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f8c75-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8c75-134">备注</span><span class="sxs-lookup"><span data-stu-id="f8c75-134">Remarks</span></span>  
 <span data-ttu-id="f8c75-135">`ModifyApplicationPolicy`两次调用方法。</span><span class="sxs-lookup"><span data-stu-id="f8c75-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="f8c75-136">第一次调用应提供的 null 值`pbNewApplicationPolicy`参数。</span><span class="sxs-lookup"><span data-stu-id="f8c75-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="f8c75-137">此调用将返回包含必需的值的`pcbNewAppPolicySize`。</span><span class="sxs-lookup"><span data-stu-id="f8c75-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="f8c75-138">第二个调用应提供此值`pcbNewAppPolicySize`，并指向该大小的缓冲区`pbNewApplicationPolicy`。</span><span class="sxs-lookup"><span data-stu-id="f8c75-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8c75-139">要求</span><span class="sxs-lookup"><span data-stu-id="f8c75-139">Requirements</span></span>  
 <span data-ttu-id="f8c75-140">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8c75-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8c75-141">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f8c75-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8c75-142">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f8c75-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8c75-143">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8c75-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8c75-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8c75-144">See Also</span></span>  
 [<span data-ttu-id="f8c75-145">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="f8c75-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
