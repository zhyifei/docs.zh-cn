---
title: IHostSecurityManager::ImpersonateLoggedOnUser 方法
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ebf9ad72f7a1b0dd7ac54afa104089182f122ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109884"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="e12ff-102">IHostSecurityManager::ImpersonateLoggedOnUser 方法</span><span class="sxs-lookup"><span data-stu-id="e12ff-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="e12ff-103">请求的代码在执行使用当前用户标识的凭据。</span><span class="sxs-lookup"><span data-stu-id="e12ff-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e12ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="e12ff-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e12ff-105">参数</span><span class="sxs-lookup"><span data-stu-id="e12ff-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="e12ff-106">[in]表示要模拟的用户的凭据的标记。</span><span class="sxs-lookup"><span data-stu-id="e12ff-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e12ff-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e12ff-107">Return Value</span></span>  
  
|<span data-ttu-id="e12ff-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e12ff-108">HRESULT</span></span>|<span data-ttu-id="e12ff-109">描述</span><span class="sxs-lookup"><span data-stu-id="e12ff-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e12ff-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e12ff-110">S_OK</span></span>|`ImpersonateLoggedOnUser` <span data-ttu-id="e12ff-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e12ff-111">returned successfully.</span></span>|  
|<span data-ttu-id="e12ff-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e12ff-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e12ff-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e12ff-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e12ff-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e12ff-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e12ff-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="e12ff-115">The call timed out.</span></span>|  
|<span data-ttu-id="e12ff-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e12ff-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e12ff-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e12ff-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e12ff-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e12ff-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e12ff-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e12ff-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e12ff-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e12ff-120">E_FAIL</span></span>|<span data-ttu-id="e12ff-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e12ff-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e12ff-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="e12ff-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e12ff-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e12ff-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e12ff-124">备注</span><span class="sxs-lookup"><span data-stu-id="e12ff-124">Remarks</span></span>  
 <span data-ttu-id="e12ff-125">调用`LogonUser`或相关的 Win32 函数来获取的句柄的当前用户标识的凭据。</span><span class="sxs-lookup"><span data-stu-id="e12ff-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="e12ff-126">`HANDLE`类型不是 COM 兼容，也就是说，其大小是特定于操作系统，，它需要自定义封送处理。</span><span class="sxs-lookup"><span data-stu-id="e12ff-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="e12ff-127">因此，此令牌是仅在 CLR 与主机之间的流程内使用。</span><span class="sxs-lookup"><span data-stu-id="e12ff-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e12ff-128">要求</span><span class="sxs-lookup"><span data-stu-id="e12ff-128">Requirements</span></span>  
 <span data-ttu-id="e12ff-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e12ff-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e12ff-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e12ff-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e12ff-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e12ff-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e12ff-132">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="e12ff-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e12ff-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="e12ff-133">See also</span></span>

- [<span data-ttu-id="e12ff-134">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="e12ff-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="e12ff-135">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="e12ff-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="e12ff-136">RevertToSelf 方法</span><span class="sxs-lookup"><span data-stu-id="e12ff-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
