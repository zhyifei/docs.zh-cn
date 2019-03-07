---
title: IHostSecurityManager::SetThreadToken 方法
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e06a76b4d51245388bf36b8127a470f55ca645fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494696"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="51992-102">IHostSecurityManager::SetThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="51992-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="51992-103">设置当前执行线程的句柄。</span><span class="sxs-lookup"><span data-stu-id="51992-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51992-104">语法</span><span class="sxs-lookup"><span data-stu-id="51992-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51992-105">参数</span><span class="sxs-lookup"><span data-stu-id="51992-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="51992-106">[in]令牌设置为当前正在执行的线程句柄。</span><span class="sxs-lookup"><span data-stu-id="51992-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51992-107">返回值</span><span class="sxs-lookup"><span data-stu-id="51992-107">Return Value</span></span>  
  
|<span data-ttu-id="51992-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51992-108">HRESULT</span></span>|<span data-ttu-id="51992-109">描述</span><span class="sxs-lookup"><span data-stu-id="51992-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51992-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="51992-110">S_OK</span></span>|<span data-ttu-id="51992-111">`SetThreadToken` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="51992-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="51992-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51992-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51992-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="51992-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51992-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51992-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51992-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="51992-115">The call timed out.</span></span>|  
|<span data-ttu-id="51992-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51992-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51992-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="51992-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51992-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51992-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51992-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="51992-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51992-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51992-120">E_FAIL</span></span>|<span data-ttu-id="51992-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="51992-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51992-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="51992-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51992-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="51992-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51992-124">备注</span><span class="sxs-lookup"><span data-stu-id="51992-124">Remarks</span></span>  
 <span data-ttu-id="51992-125">`IHostSecurityManager::SetThreadToken` 行为同样具有相同名称的相应的 Win32 函数相似，Win32 函数允许调用方将句柄传递给任意线程，而`IHostSecurityManager::SetThreadToken`可以将令牌仅与当前执行线程关联。</span><span class="sxs-lookup"><span data-stu-id="51992-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="51992-126">`HANDLE`类型不是 COM 兼容; 即，其大小是特定于操作系统，它需要自定义封送处理。</span><span class="sxs-lookup"><span data-stu-id="51992-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="51992-127">因此，此令牌是仅在 CLR 与主机之间的流程内使用。</span><span class="sxs-lookup"><span data-stu-id="51992-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51992-128">要求</span><span class="sxs-lookup"><span data-stu-id="51992-128">Requirements</span></span>  
 <span data-ttu-id="51992-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51992-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51992-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="51992-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51992-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="51992-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51992-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51992-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51992-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="51992-133">See also</span></span>
- [<span data-ttu-id="51992-134">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="51992-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="51992-135">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="51992-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
