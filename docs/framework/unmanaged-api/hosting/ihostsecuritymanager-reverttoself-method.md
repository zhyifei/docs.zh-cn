---
title: IHostSecurityManager::RevertToSelf 方法
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c34d9243e4ed7ed2492784154b157189c7d22cd2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440575"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="62960-102">IHostSecurityManager::RevertToSelf 方法</span><span class="sxs-lookup"><span data-stu-id="62960-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="62960-103">终止模拟当前用户标识，并返回原始线程令牌。</span><span class="sxs-lookup"><span data-stu-id="62960-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62960-104">语法</span><span class="sxs-lookup"><span data-stu-id="62960-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="62960-105">返回值</span><span class="sxs-lookup"><span data-stu-id="62960-105">Return Value</span></span>  
  
|<span data-ttu-id="62960-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62960-106">HRESULT</span></span>|<span data-ttu-id="62960-107">描述</span><span class="sxs-lookup"><span data-stu-id="62960-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62960-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="62960-108">S_OK</span></span>|<span data-ttu-id="62960-109">`RevertToSelf` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="62960-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="62960-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62960-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62960-111">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="62960-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62960-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62960-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62960-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="62960-113">The call timed out.</span></span>|  
|<span data-ttu-id="62960-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62960-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62960-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="62960-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62960-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62960-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62960-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="62960-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62960-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62960-118">E_FAIL</span></span>|<span data-ttu-id="62960-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="62960-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62960-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="62960-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62960-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="62960-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62960-122">备注</span><span class="sxs-lookup"><span data-stu-id="62960-122">Remarks</span></span>  
 <span data-ttu-id="62960-123">`RevertToSelf` 调用以返回到原始线程令牌中，在以前调用后[ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="62960-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62960-124">要求</span><span class="sxs-lookup"><span data-stu-id="62960-124">Requirements</span></span>  
 <span data-ttu-id="62960-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62960-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62960-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62960-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62960-127">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="62960-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62960-128">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62960-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62960-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="62960-129">See Also</span></span>  
 [<span data-ttu-id="62960-130">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="62960-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="62960-131">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="62960-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="62960-132">ImpersonateLoggedOnUser 方法</span><span class="sxs-lookup"><span data-stu-id="62960-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
