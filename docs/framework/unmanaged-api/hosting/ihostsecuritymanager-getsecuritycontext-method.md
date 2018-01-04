---
title: "IHostSecurityManager::GetSecurityContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.GetSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a5fcdf0d0244694a52cf1964d0e7c4be692df2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="4caff-102">IHostSecurityManager::GetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="4caff-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="4caff-103">获取请求[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)从主机。</span><span class="sxs-lookup"><span data-stu-id="4caff-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4caff-104">语法</span><span class="sxs-lookup"><span data-stu-id="4caff-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4caff-105">参数</span><span class="sxs-lookup"><span data-stu-id="4caff-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="4caff-106">[in]之一[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)值，指示要返回的安全上下文的类型。</span><span class="sxs-lookup"><span data-stu-id="4caff-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="4caff-107">[out]接口指针的地址`IHostSecurityContext`的`eContextType`。</span><span class="sxs-lookup"><span data-stu-id="4caff-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4caff-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4caff-108">Return Value</span></span>  
  
|<span data-ttu-id="4caff-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4caff-109">HRESULT</span></span>|<span data-ttu-id="4caff-110">描述</span><span class="sxs-lookup"><span data-stu-id="4caff-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4caff-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4caff-111">S_OK</span></span>|<span data-ttu-id="4caff-112">`GetSecurityContext`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4caff-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="4caff-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4caff-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4caff-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4caff-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4caff-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4caff-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4caff-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="4caff-116">The call timed out.</span></span>|  
|<span data-ttu-id="4caff-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4caff-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4caff-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4caff-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4caff-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4caff-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4caff-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="4caff-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4caff-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4caff-121">E_FAIL</span></span>|<span data-ttu-id="4caff-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4caff-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4caff-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="4caff-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4caff-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4caff-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4caff-125">备注</span><span class="sxs-lookup"><span data-stu-id="4caff-125">Remarks</span></span>  
 <span data-ttu-id="4caff-126">主机可以控制的 CLR 和用户代码对线程标记的所有代码访问。</span><span class="sxs-lookup"><span data-stu-id="4caff-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="4caff-127">它还可确保完整的安全性在异步操作或具有受限制的代码访问权限的代码点间传递上下文信息。</span><span class="sxs-lookup"><span data-stu-id="4caff-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="4caff-128">`IHostSecurityContext`封装此安全上下文信息，这就是不透明的 CLR。</span><span class="sxs-lookup"><span data-stu-id="4caff-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="4caff-129">CLR 捕获此信息并将其移动在线程池工作项调度、 终结器执行和模块和类的构造。</span><span class="sxs-lookup"><span data-stu-id="4caff-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4caff-130">惠?</span><span class="sxs-lookup"><span data-stu-id="4caff-130">Requirements</span></span>  
 <span data-ttu-id="4caff-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4caff-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4caff-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4caff-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4caff-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4caff-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4caff-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4caff-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4caff-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="4caff-135">See Also</span></span>  
 [<span data-ttu-id="4caff-136">EContextType 枚举</span><span class="sxs-lookup"><span data-stu-id="4caff-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="4caff-137">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="4caff-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="4caff-138">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="4caff-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
