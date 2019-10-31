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
ms.openlocfilehash: 93051ca9a0b6f57f41d0d17335a838fe92832d8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121500"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="02a7d-102">IHostSecurityManager::ImpersonateLoggedOnUser 方法</span><span class="sxs-lookup"><span data-stu-id="02a7d-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="02a7d-103">请求使用当前用户标识的凭据执行代码。</span><span class="sxs-lookup"><span data-stu-id="02a7d-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a7d-104">语法</span><span class="sxs-lookup"><span data-stu-id="02a7d-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02a7d-105">参数</span><span class="sxs-lookup"><span data-stu-id="02a7d-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="02a7d-106">中一个标记，表示要模拟的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="02a7d-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02a7d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="02a7d-107">Return Value</span></span>  
  
|<span data-ttu-id="02a7d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02a7d-108">HRESULT</span></span>|<span data-ttu-id="02a7d-109">描述</span><span class="sxs-lookup"><span data-stu-id="02a7d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02a7d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="02a7d-110">S_OK</span></span>|<span data-ttu-id="02a7d-111">`ImpersonateLoggedOnUser` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="02a7d-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="02a7d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02a7d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02a7d-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="02a7d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02a7d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02a7d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02a7d-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="02a7d-115">The call timed out.</span></span>|  
|<span data-ttu-id="02a7d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02a7d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02a7d-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="02a7d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02a7d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02a7d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02a7d-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="02a7d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02a7d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02a7d-120">E_FAIL</span></span>|<span data-ttu-id="02a7d-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="02a7d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02a7d-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="02a7d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02a7d-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="02a7d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02a7d-124">备注</span><span class="sxs-lookup"><span data-stu-id="02a7d-124">Remarks</span></span>  
 <span data-ttu-id="02a7d-125">调用 `LogonUser` 或相关的 Win32 函数以获取当前用户标识的凭据的句柄。</span><span class="sxs-lookup"><span data-stu-id="02a7d-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="02a7d-126">`HANDLE` 类型不符合 COM 要求，也就是说，其大小特定于操作系统，并需要自定义封送处理。</span><span class="sxs-lookup"><span data-stu-id="02a7d-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="02a7d-127">因此，此令牌仅在该进程内的 CLR 和主机之间使用。</span><span class="sxs-lookup"><span data-stu-id="02a7d-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02a7d-128">要求</span><span class="sxs-lookup"><span data-stu-id="02a7d-128">Requirements</span></span>  
 <span data-ttu-id="02a7d-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02a7d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a7d-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="02a7d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02a7d-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="02a7d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02a7d-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a7d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a7d-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="02a7d-133">See also</span></span>

- [<span data-ttu-id="02a7d-134">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="02a7d-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="02a7d-135">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="02a7d-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="02a7d-136">RevertToSelf 方法</span><span class="sxs-lookup"><span data-stu-id="02a7d-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
