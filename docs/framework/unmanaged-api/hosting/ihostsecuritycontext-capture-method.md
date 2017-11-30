---
title: "IHostSecurityContext::Capture 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext.Capture
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 100ce151b81fb240434b1072be8fe8c354f85440
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="8194c-102">IHostSecurityContext::Capture 方法</span><span class="sxs-lookup"><span data-stu-id="8194c-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="8194c-103">获取的复本[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)实例返回到调用[ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)。</span><span class="sxs-lookup"><span data-stu-id="8194c-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8194c-104">语法</span><span class="sxs-lookup"><span data-stu-id="8194c-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8194c-105">参数</span><span class="sxs-lookup"><span data-stu-id="8194c-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="8194c-106">[out]指向的地址的克隆`IHostSecurityContext`要捕获的对象。</span><span class="sxs-lookup"><span data-stu-id="8194c-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8194c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8194c-107">Return Value</span></span>  
  
|<span data-ttu-id="8194c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8194c-108">HRESULT</span></span>|<span data-ttu-id="8194c-109">描述</span><span class="sxs-lookup"><span data-stu-id="8194c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8194c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8194c-110">S_OK</span></span>|<span data-ttu-id="8194c-111">`Capture`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8194c-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="8194c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8194c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8194c-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8194c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8194c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8194c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8194c-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="8194c-115">The call timed out.</span></span>|  
|<span data-ttu-id="8194c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8194c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8194c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8194c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8194c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8194c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8194c-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="8194c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8194c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8194c-120">E_FAIL</span></span>|<span data-ttu-id="8194c-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8194c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8194c-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="8194c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8194c-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8194c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8194c-124">备注</span><span class="sxs-lookup"><span data-stu-id="8194c-124">Remarks</span></span>  
 <span data-ttu-id="8194c-125">从返回的接口指针`Capture`是捕获的上下文的克隆。</span><span class="sxs-lookup"><span data-stu-id="8194c-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="8194c-126">此信息已移跨异步代码点，其生存期被分开下面，对其进行调用的指针。</span><span class="sxs-lookup"><span data-stu-id="8194c-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="8194c-127">因此可以释放原始指针。</span><span class="sxs-lookup"><span data-stu-id="8194c-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8194c-128">要求</span><span class="sxs-lookup"><span data-stu-id="8194c-128">Requirements</span></span>  
 <span data-ttu-id="8194c-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8194c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8194c-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8194c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8194c-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8194c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8194c-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8194c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8194c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8194c-133">See Also</span></span>  
 [<span data-ttu-id="8194c-134">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="8194c-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="8194c-135">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="8194c-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
