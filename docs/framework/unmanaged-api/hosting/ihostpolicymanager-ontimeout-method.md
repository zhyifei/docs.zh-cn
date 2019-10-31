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
ms.openlocfilehash: e8a14dd6a6d196cea9caa6be669b2b75a167eca8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141113"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="7870e-102">IHostPolicyManager::OnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="7870e-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="7870e-103">向宿主通知公共语言运行时（CLR）将通过对[ICLRPolicyManager：： SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)方法的调用来执行指定的操作，以响应超时。</span><span class="sxs-lookup"><span data-stu-id="7870e-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7870e-104">语法</span><span class="sxs-lookup"><span data-stu-id="7870e-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7870e-105">参数</span><span class="sxs-lookup"><span data-stu-id="7870e-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="7870e-106">中[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值之一，指示已超时的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="7870e-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="7870e-107">中[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值之一，指示 CLR 响应超时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="7870e-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7870e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7870e-108">Return Value</span></span>  
  
|<span data-ttu-id="7870e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7870e-109">HRESULT</span></span>|<span data-ttu-id="7870e-110">描述</span><span class="sxs-lookup"><span data-stu-id="7870e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7870e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7870e-111">S_OK</span></span>|<span data-ttu-id="7870e-112">`OnTimeout` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="7870e-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="7870e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7870e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7870e-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7870e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7870e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7870e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7870e-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="7870e-116">The call timed out.</span></span>|  
|<span data-ttu-id="7870e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7870e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7870e-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7870e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7870e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7870e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7870e-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="7870e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7870e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7870e-121">E_FAIL</span></span>|<span data-ttu-id="7870e-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7870e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7870e-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="7870e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7870e-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7870e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7870e-125">要求</span><span class="sxs-lookup"><span data-stu-id="7870e-125">Requirements</span></span>  
 <span data-ttu-id="7870e-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7870e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7870e-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7870e-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7870e-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7870e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7870e-129">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7870e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7870e-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="7870e-130">See also</span></span>

- [<span data-ttu-id="7870e-131">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="7870e-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="7870e-132">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="7870e-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="7870e-133">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="7870e-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="7870e-134">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="7870e-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
