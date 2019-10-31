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
ms.openlocfilehash: aa17f637ef71373697db5ce66e4a6540c5cc5fbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139492"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="7605e-102">IHostSecurityManager::SetThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="7605e-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="7605e-103">设置当前正在执行的线程的句柄。</span><span class="sxs-lookup"><span data-stu-id="7605e-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7605e-104">语法</span><span class="sxs-lookup"><span data-stu-id="7605e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7605e-105">参数</span><span class="sxs-lookup"><span data-stu-id="7605e-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="7605e-106">中要为当前正在执行的线程设置的标记的句柄。</span><span class="sxs-lookup"><span data-stu-id="7605e-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7605e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7605e-107">Return Value</span></span>  
  
|<span data-ttu-id="7605e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7605e-108">HRESULT</span></span>|<span data-ttu-id="7605e-109">描述</span><span class="sxs-lookup"><span data-stu-id="7605e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7605e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7605e-110">S_OK</span></span>|<span data-ttu-id="7605e-111">`SetThreadToken` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="7605e-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="7605e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7605e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7605e-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7605e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7605e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7605e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7605e-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="7605e-115">The call timed out.</span></span>|  
|<span data-ttu-id="7605e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7605e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7605e-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7605e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7605e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7605e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7605e-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="7605e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7605e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7605e-120">E_FAIL</span></span>|<span data-ttu-id="7605e-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7605e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7605e-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="7605e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7605e-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7605e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7605e-124">备注</span><span class="sxs-lookup"><span data-stu-id="7605e-124">Remarks</span></span>  
 <span data-ttu-id="7605e-125">`IHostSecurityManager::SetThreadToken` 的行为类似于具有相同名称的对应 Win32 函数，不同之处在于 Win32 函数允许调用方将句柄传入任意线程，而 `IHostSecurityManager::SetThreadToken` 只能将标记与当前正在执行的线程关联。</span><span class="sxs-lookup"><span data-stu-id="7605e-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="7605e-126">`HANDLE` 类型不符合 COM 要求;也就是说，其大小特定于操作系统并且需要自定义封送处理。</span><span class="sxs-lookup"><span data-stu-id="7605e-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="7605e-127">因此，此令牌仅在该进程内的 CLR 和主机之间使用。</span><span class="sxs-lookup"><span data-stu-id="7605e-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7605e-128">要求</span><span class="sxs-lookup"><span data-stu-id="7605e-128">Requirements</span></span>  
 <span data-ttu-id="7605e-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7605e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7605e-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7605e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7605e-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7605e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7605e-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7605e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7605e-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="7605e-133">See also</span></span>

- [<span data-ttu-id="7605e-134">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="7605e-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="7605e-135">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="7605e-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
