---
title: IHostSecurityManager::GetSecurityContext 方法
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d17609e585f6e0ecd685d893bb0f8b3e4c0fe0cc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484820"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="0e363-102">IHostSecurityManager::GetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="0e363-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="0e363-103">获取所请求[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)从主机。</span><span class="sxs-lookup"><span data-stu-id="0e363-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e363-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e363-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e363-105">参数</span><span class="sxs-lookup"><span data-stu-id="0e363-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="0e363-106">[in]之一[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)值，它指示哪种类型的安全上下文，以返回。</span><span class="sxs-lookup"><span data-stu-id="0e363-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="0e363-107">[out]接口指针的地址`IHostSecurityContext`的`eContextType`。</span><span class="sxs-lookup"><span data-stu-id="0e363-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e363-108">返回值</span><span class="sxs-lookup"><span data-stu-id="0e363-108">Return Value</span></span>  
  
|<span data-ttu-id="0e363-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e363-109">HRESULT</span></span>|<span data-ttu-id="0e363-110">描述</span><span class="sxs-lookup"><span data-stu-id="0e363-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e363-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e363-111">S_OK</span></span>|<span data-ttu-id="0e363-112">`GetSecurityContext` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0e363-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="0e363-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e363-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e363-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0e363-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e363-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e363-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e363-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="0e363-116">The call timed out.</span></span>|  
|<span data-ttu-id="0e363-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e363-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e363-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0e363-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e363-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e363-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e363-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0e363-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e363-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e363-121">E_FAIL</span></span>|<span data-ttu-id="0e363-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0e363-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e363-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="0e363-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e363-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0e363-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e363-125">备注</span><span class="sxs-lookup"><span data-stu-id="0e363-125">Remarks</span></span>  
 <span data-ttu-id="0e363-126">主机可以通过 CLR 和用户代码控制对线程令牌的所有代码访问权限。</span><span class="sxs-lookup"><span data-stu-id="0e363-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="0e363-127">它还可确保完整的安全跨异步操作或具有受限制的代码访问权限的代码点传递上下文信息。</span><span class="sxs-lookup"><span data-stu-id="0e363-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="0e363-128">`IHostSecurityContext` 封装此安全上下文信息，这是不透明的 CLR。</span><span class="sxs-lookup"><span data-stu-id="0e363-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="0e363-129">CLR 捕获此信息并将其移动多个线程池工作项调度、 终结器执行和模块和类构造。</span><span class="sxs-lookup"><span data-stu-id="0e363-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e363-130">要求</span><span class="sxs-lookup"><span data-stu-id="0e363-130">Requirements</span></span>  
 <span data-ttu-id="0e363-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e363-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e363-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0e363-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e363-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0e363-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e363-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e363-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e363-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e363-135">See also</span></span>
- [<span data-ttu-id="0e363-136">EContextType 枚举</span><span class="sxs-lookup"><span data-stu-id="0e363-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="0e363-137">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="0e363-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="0e363-138">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="0e363-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
