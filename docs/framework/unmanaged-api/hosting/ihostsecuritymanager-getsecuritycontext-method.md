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
ms.openlocfilehash: 7198698edce48546c4f9a82ace18d5a6e71891ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176248"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="eb3fc-102">IHostSecurityManager::GetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="eb3fc-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="eb3fc-103">从主机获取请求的[IHost 安全上下文](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb3fc-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb3fc-105">parameters</span><span class="sxs-lookup"><span data-stu-id="eb3fc-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="eb3fc-106">[在][EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)值之一，指示要返回的安全上下文的类型。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="eb3fc-107">[出]指向 的`IHostSecurityContext`接口指针的地址`eContextType`。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb3fc-108">返回值</span><span class="sxs-lookup"><span data-stu-id="eb3fc-108">Return Value</span></span>  
  
|<span data-ttu-id="eb3fc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb3fc-109">HRESULT</span></span>|<span data-ttu-id="eb3fc-110">说明</span><span class="sxs-lookup"><span data-stu-id="eb3fc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb3fc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb3fc-111">S_OK</span></span>|<span data-ttu-id="eb3fc-112">`GetSecurityContext`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="eb3fc-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eb3fc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eb3fc-114">公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eb3fc-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eb3fc-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eb3fc-116">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-116">The call timed out.</span></span>|  
|<span data-ttu-id="eb3fc-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eb3fc-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eb3fc-118">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eb3fc-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eb3fc-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eb3fc-120">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eb3fc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eb3fc-121">E_FAIL</span></span>|<span data-ttu-id="eb3fc-122">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eb3fc-123">当方法返回E_FAIL时，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eb3fc-124">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb3fc-125">备注</span><span class="sxs-lookup"><span data-stu-id="eb3fc-125">Remarks</span></span>  
 <span data-ttu-id="eb3fc-126">主机可以通过 CLR 和用户代码控制对线程令牌的所有代码访问。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="eb3fc-127">它还可确保在具有受限代码访问权限的异步操作或代码点传递完整的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="eb3fc-128">`IHostSecurityContext`封装此安全上下文信息，这些信息对 CLR 是不透明的。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="eb3fc-129">CLR 捕获此信息并将其跨线程池辅助工项调度、终结器执行以及模块和类构造移动。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb3fc-130">要求</span><span class="sxs-lookup"><span data-stu-id="eb3fc-130">Requirements</span></span>  
 <span data-ttu-id="eb3fc-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb3fc-132">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eb3fc-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb3fc-133">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="eb3fc-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb3fc-134">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb3fc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3fc-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb3fc-135">See also</span></span>

- [<span data-ttu-id="eb3fc-136">EContextType 枚举</span><span class="sxs-lookup"><span data-stu-id="eb3fc-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="eb3fc-137">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="eb3fc-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="eb3fc-138">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="eb3fc-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
