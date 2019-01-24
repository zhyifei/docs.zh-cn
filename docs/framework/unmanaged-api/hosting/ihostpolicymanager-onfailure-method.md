---
title: IHostPolicyManager::OnFailure 方法
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6277c14901e57e44716911a3ae7dfe1bfe92182a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722323"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="7a145-102">IHostPolicyManager::OnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="7a145-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="7a145-103">通知公共语言运行时 (CLR) 是即将执行通过调用指定的操作主机[iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)方法以响应的资源分配或回收故障。</span><span class="sxs-lookup"><span data-stu-id="7a145-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a145-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a145-104">Syntax</span></span>  
  
```  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a145-105">参数</span><span class="sxs-lookup"><span data-stu-id="7a145-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="7a145-106">[in]之一[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值，它指示的故障回复 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="7a145-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="7a145-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，该值指示操作 CLR 正在响应`failure`。</span><span class="sxs-lookup"><span data-stu-id="7a145-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a145-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7a145-108">Return Value</span></span>  
  
|<span data-ttu-id="7a145-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a145-109">HRESULT</span></span>|<span data-ttu-id="7a145-110">描述</span><span class="sxs-lookup"><span data-stu-id="7a145-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a145-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a145-111">S_OK</span></span>|<span data-ttu-id="7a145-112">`OnFailure` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7a145-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="7a145-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a145-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a145-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7a145-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a145-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a145-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a145-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="7a145-116">The call timed out.</span></span>|  
|<span data-ttu-id="7a145-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a145-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a145-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7a145-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a145-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a145-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a145-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="7a145-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a145-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a145-121">E_FAIL</span></span>|<span data-ttu-id="7a145-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7a145-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a145-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="7a145-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a145-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7a145-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a145-125">要求</span><span class="sxs-lookup"><span data-stu-id="7a145-125">Requirements</span></span>  
 <span data-ttu-id="7a145-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a145-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a145-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7a145-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a145-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7a145-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a145-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a145-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a145-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a145-130">See also</span></span>
- [<span data-ttu-id="7a145-131">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="7a145-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="7a145-132">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="7a145-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="7a145-133">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="7a145-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="7a145-134">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="7a145-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
