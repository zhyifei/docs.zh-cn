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
ms.openlocfilehash: ada12a35691e0897a44f4f00e2e439fc08ef18af
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803908"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="777bd-102">IHostSecurityManager::ImpersonateLoggedOnUser 方法</span><span class="sxs-lookup"><span data-stu-id="777bd-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="777bd-103">请求使用当前用户标识的凭据执行代码。</span><span class="sxs-lookup"><span data-stu-id="777bd-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="777bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="777bd-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="777bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="777bd-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="777bd-106">中一个标记，表示要模拟的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="777bd-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="777bd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="777bd-107">Return Value</span></span>  
  
|<span data-ttu-id="777bd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="777bd-108">HRESULT</span></span>|<span data-ttu-id="777bd-109">说明</span><span class="sxs-lookup"><span data-stu-id="777bd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="777bd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="777bd-110">S_OK</span></span>|<span data-ttu-id="777bd-111">`ImpersonateLoggedOnUser`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="777bd-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="777bd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="777bd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="777bd-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="777bd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="777bd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="777bd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="777bd-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="777bd-115">The call timed out.</span></span>|  
|<span data-ttu-id="777bd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="777bd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="777bd-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="777bd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="777bd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="777bd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="777bd-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="777bd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="777bd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="777bd-120">E_FAIL</span></span>|<span data-ttu-id="777bd-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="777bd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="777bd-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="777bd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="777bd-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="777bd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="777bd-124">备注</span><span class="sxs-lookup"><span data-stu-id="777bd-124">Remarks</span></span>  
 <span data-ttu-id="777bd-125">调用 `LogonUser` 或相关的 Win32 函数获取当前用户标识的凭据的句柄。</span><span class="sxs-lookup"><span data-stu-id="777bd-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="777bd-126">`HANDLE`类型不符合 COM 要求，也就是说，其大小特定于操作系统，并需要自定义封送处理。</span><span class="sxs-lookup"><span data-stu-id="777bd-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="777bd-127">因此，此令牌仅在该进程内的 CLR 和主机之间使用。</span><span class="sxs-lookup"><span data-stu-id="777bd-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="777bd-128">要求</span><span class="sxs-lookup"><span data-stu-id="777bd-128">Requirements</span></span>  
 <span data-ttu-id="777bd-129">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="777bd-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="777bd-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="777bd-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="777bd-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="777bd-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="777bd-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="777bd-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="777bd-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="777bd-133">See also</span></span>

- [<span data-ttu-id="777bd-134">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="777bd-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="777bd-135">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="777bd-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="777bd-136">RevertToSelf 方法</span><span class="sxs-lookup"><span data-stu-id="777bd-136">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)
