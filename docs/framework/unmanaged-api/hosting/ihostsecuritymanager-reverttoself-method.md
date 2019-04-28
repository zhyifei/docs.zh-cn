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
ms.openlocfilehash: d282f6d37a2be8a41f4fbda579b3b467b9bfc8ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696679"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="11c1a-102">IHostSecurityManager::RevertToSelf 方法</span><span class="sxs-lookup"><span data-stu-id="11c1a-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="11c1a-103">终止模拟当前用户标识，并返回原始线程标记。</span><span class="sxs-lookup"><span data-stu-id="11c1a-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c1a-104">语法</span><span class="sxs-lookup"><span data-stu-id="11c1a-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="11c1a-105">返回值</span><span class="sxs-lookup"><span data-stu-id="11c1a-105">Return Value</span></span>  
  
|<span data-ttu-id="11c1a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11c1a-106">HRESULT</span></span>|<span data-ttu-id="11c1a-107">描述</span><span class="sxs-lookup"><span data-stu-id="11c1a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11c1a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="11c1a-108">S_OK</span></span>|<span data-ttu-id="11c1a-109">`RevertToSelf` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="11c1a-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="11c1a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11c1a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11c1a-111">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="11c1a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11c1a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11c1a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11c1a-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="11c1a-113">The call timed out.</span></span>|  
|<span data-ttu-id="11c1a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11c1a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11c1a-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="11c1a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11c1a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11c1a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11c1a-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="11c1a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11c1a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11c1a-118">E_FAIL</span></span>|<span data-ttu-id="11c1a-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="11c1a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="11c1a-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="11c1a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11c1a-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="11c1a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11c1a-122">备注</span><span class="sxs-lookup"><span data-stu-id="11c1a-122">Remarks</span></span>  
 <span data-ttu-id="11c1a-123">`RevertToSelf` 调用以早期调用之后返回到原始线程标记中， [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="11c1a-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11c1a-124">要求</span><span class="sxs-lookup"><span data-stu-id="11c1a-124">Requirements</span></span>  
 <span data-ttu-id="11c1a-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11c1a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11c1a-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11c1a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11c1a-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="11c1a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11c1a-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11c1a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c1a-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="11c1a-129">See also</span></span>

- [<span data-ttu-id="11c1a-130">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="11c1a-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="11c1a-131">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="11c1a-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="11c1a-132">ImpersonateLoggedOnUser 方法</span><span class="sxs-lookup"><span data-stu-id="11c1a-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
