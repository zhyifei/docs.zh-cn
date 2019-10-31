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
ms.openlocfilehash: 3bb65d747d7cdc81bd534108f6189eb1c94e3b15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128548"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="5ad44-102">IHostPolicyManager::OnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="5ad44-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="5ad44-103">向宿主通知公共语言运行时（CLR）将对[ICLRPolicyManager：： SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)方法的调用所指定的操作，以响应资源分配或回收失败。</span><span class="sxs-lookup"><span data-stu-id="5ad44-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ad44-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ad44-104">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ad44-105">参数</span><span class="sxs-lookup"><span data-stu-id="5ad44-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="5ad44-106">中[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)值之一，指示 CLR 响应的失败类型。</span><span class="sxs-lookup"><span data-stu-id="5ad44-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="5ad44-107">中[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值之一，指示 CLR 响应 `failure`所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="5ad44-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ad44-108">返回值</span><span class="sxs-lookup"><span data-stu-id="5ad44-108">Return Value</span></span>  
  
|<span data-ttu-id="5ad44-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ad44-109">HRESULT</span></span>|<span data-ttu-id="5ad44-110">描述</span><span class="sxs-lookup"><span data-stu-id="5ad44-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ad44-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ad44-111">S_OK</span></span>|<span data-ttu-id="5ad44-112">`OnFailure` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="5ad44-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="5ad44-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5ad44-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5ad44-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5ad44-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5ad44-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5ad44-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5ad44-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="5ad44-116">The call timed out.</span></span>|  
|<span data-ttu-id="5ad44-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5ad44-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5ad44-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5ad44-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5ad44-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5ad44-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5ad44-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="5ad44-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5ad44-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5ad44-121">E_FAIL</span></span>|<span data-ttu-id="5ad44-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5ad44-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5ad44-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="5ad44-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5ad44-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5ad44-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ad44-125">要求</span><span class="sxs-lookup"><span data-stu-id="5ad44-125">Requirements</span></span>  
 <span data-ttu-id="5ad44-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5ad44-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ad44-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5ad44-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ad44-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5ad44-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ad44-129">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ad44-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad44-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ad44-130">See also</span></span>

- [<span data-ttu-id="5ad44-131">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="5ad44-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="5ad44-132">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="5ad44-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="5ad44-133">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="5ad44-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="5ad44-134">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="5ad44-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
