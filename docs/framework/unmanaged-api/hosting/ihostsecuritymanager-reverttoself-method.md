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
ms.openlocfilehash: b896c5509cc4862a6416381f89bc04a28959e091
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121456"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="752bb-102">IHostSecurityManager::RevertToSelf 方法</span><span class="sxs-lookup"><span data-stu-id="752bb-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="752bb-103">终止当前用户标识的模拟并返回原始线程标记。</span><span class="sxs-lookup"><span data-stu-id="752bb-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="752bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="752bb-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="752bb-105">返回值</span><span class="sxs-lookup"><span data-stu-id="752bb-105">Return Value</span></span>  
  
|<span data-ttu-id="752bb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="752bb-106">HRESULT</span></span>|<span data-ttu-id="752bb-107">描述</span><span class="sxs-lookup"><span data-stu-id="752bb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="752bb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="752bb-108">S_OK</span></span>|<span data-ttu-id="752bb-109">`RevertToSelf` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="752bb-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="752bb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="752bb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="752bb-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="752bb-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="752bb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="752bb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="752bb-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="752bb-113">The call timed out.</span></span>|  
|<span data-ttu-id="752bb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="752bb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="752bb-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="752bb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="752bb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="752bb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="752bb-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="752bb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="752bb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="752bb-118">E_FAIL</span></span>|<span data-ttu-id="752bb-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="752bb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="752bb-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="752bb-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="752bb-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="752bb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="752bb-122">备注</span><span class="sxs-lookup"><span data-stu-id="752bb-122">Remarks</span></span>  
 <span data-ttu-id="752bb-123">调用[ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)方法后，将调用 `RevertToSelf` 返回到原始线程标记。</span><span class="sxs-lookup"><span data-stu-id="752bb-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="752bb-124">要求</span><span class="sxs-lookup"><span data-stu-id="752bb-124">Requirements</span></span>  
 <span data-ttu-id="752bb-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="752bb-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="752bb-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="752bb-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="752bb-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="752bb-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="752bb-128">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="752bb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="752bb-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="752bb-129">See also</span></span>

- [<span data-ttu-id="752bb-130">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="752bb-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="752bb-131">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="752bb-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="752bb-132">ImpersonateLoggedOnUser 方法</span><span class="sxs-lookup"><span data-stu-id="752bb-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
