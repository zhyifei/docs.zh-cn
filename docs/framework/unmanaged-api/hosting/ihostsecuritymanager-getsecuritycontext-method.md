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
ms.openlocfilehash: 66aab8081a5cce8c5ba986470bc91eb0604781a5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121506"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="4bec5-102">IHostSecurityManager::GetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="4bec5-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="4bec5-103">从主机获取请求的[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="4bec5-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bec5-104">语法</span><span class="sxs-lookup"><span data-stu-id="4bec5-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bec5-105">参数</span><span class="sxs-lookup"><span data-stu-id="4bec5-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="4bec5-106">中[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)值之一，指示要返回的安全上下文的类型。</span><span class="sxs-lookup"><span data-stu-id="4bec5-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="4bec5-107">弄指向 `eContextType``IHostSecurityContext` 的接口指针的地址。</span><span class="sxs-lookup"><span data-stu-id="4bec5-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bec5-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4bec5-108">Return Value</span></span>  
  
|<span data-ttu-id="4bec5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4bec5-109">HRESULT</span></span>|<span data-ttu-id="4bec5-110">描述</span><span class="sxs-lookup"><span data-stu-id="4bec5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4bec5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4bec5-111">S_OK</span></span>|<span data-ttu-id="4bec5-112">`GetSecurityContext` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="4bec5-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="4bec5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4bec5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4bec5-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4bec5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4bec5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4bec5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4bec5-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="4bec5-116">The call timed out.</span></span>|  
|<span data-ttu-id="4bec5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4bec5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4bec5-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4bec5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4bec5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4bec5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4bec5-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="4bec5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4bec5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4bec5-121">E_FAIL</span></span>|<span data-ttu-id="4bec5-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4bec5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4bec5-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="4bec5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4bec5-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4bec5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bec5-125">备注</span><span class="sxs-lookup"><span data-stu-id="4bec5-125">Remarks</span></span>  
 <span data-ttu-id="4bec5-126">宿主可以通过 CLR 和用户代码控制对线程标记的所有代码访问。</span><span class="sxs-lookup"><span data-stu-id="4bec5-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="4bec5-127">它还可以确保在异步操作或代码点之间跨受限制的代码访问传递完整的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="4bec5-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="4bec5-128">`IHostSecurityContext` 封装此安全上下文信息，这对于 CLR 是不透明的。</span><span class="sxs-lookup"><span data-stu-id="4bec5-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="4bec5-129">CLR 捕获此信息，并在线程池辅助角色项调度、终结器执行以及模块和类构造之间移动。</span><span class="sxs-lookup"><span data-stu-id="4bec5-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bec5-130">要求</span><span class="sxs-lookup"><span data-stu-id="4bec5-130">Requirements</span></span>  
 <span data-ttu-id="4bec5-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4bec5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bec5-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4bec5-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4bec5-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="4bec5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4bec5-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bec5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bec5-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bec5-135">See also</span></span>

- [<span data-ttu-id="4bec5-136">EContextType 枚举</span><span class="sxs-lookup"><span data-stu-id="4bec5-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="4bec5-137">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="4bec5-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="4bec5-138">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="4bec5-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
