---
title: IHostPolicyManager::OnTimeout 方法
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2badb7e1882e05678328b834b8dd094808548c9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638790"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="bd4c3-102">IHostPolicyManager::OnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="bd4c3-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="bd4c3-103">通知公共语言运行时 (CLR) 是即将执行通过调用指定的操作主机[iclrpolicymanager:: Setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)方法以响应超时。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd4c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd4c3-104">Syntax</span></span>  
  
```  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd4c3-105">参数</span><span class="sxs-lookup"><span data-stu-id="bd4c3-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="bd4c3-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，它指示类型的操作，操作已超时。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="bd4c3-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示操作 CLR 正在响应超时。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd4c3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="bd4c3-108">Return Value</span></span>  
  
|<span data-ttu-id="bd4c3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd4c3-109">HRESULT</span></span>|<span data-ttu-id="bd4c3-110">描述</span><span class="sxs-lookup"><span data-stu-id="bd4c3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd4c3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd4c3-111">S_OK</span></span>|<span data-ttu-id="bd4c3-112">`OnTimeout` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="bd4c3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bd4c3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd4c3-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd4c3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd4c3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd4c3-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-116">The call timed out.</span></span>|  
|<span data-ttu-id="bd4c3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd4c3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd4c3-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd4c3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd4c3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd4c3-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd4c3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd4c3-121">E_FAIL</span></span>|<span data-ttu-id="bd4c3-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd4c3-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd4c3-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd4c3-125">要求</span><span class="sxs-lookup"><span data-stu-id="bd4c3-125">Requirements</span></span>  
 <span data-ttu-id="bd4c3-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd4c3-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd4c3-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd4c3-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd4c3-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bd4c3-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd4c3-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd4c3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd4c3-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd4c3-130">See also</span></span>
- [<span data-ttu-id="bd4c3-131">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="bd4c3-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="bd4c3-132">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="bd4c3-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="bd4c3-133">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="bd4c3-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="bd4c3-134">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="bd4c3-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
