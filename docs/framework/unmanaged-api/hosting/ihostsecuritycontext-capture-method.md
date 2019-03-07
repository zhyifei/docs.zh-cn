---
title: IHostSecurityContext::Capture 方法
ms.date: 03/30/2017
api_name:
- IHostSecurityContext.Capture
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92b593248a7a196247a5b4c71a90cd8944665bbe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485273"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="dbddd-102">IHostSecurityContext::Capture 方法</span><span class="sxs-lookup"><span data-stu-id="dbddd-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="dbddd-103">获取的克隆[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)实例返回到调用[ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)。</span><span class="sxs-lookup"><span data-stu-id="dbddd-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbddd-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbddd-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbddd-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbddd-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="dbddd-106">[out]指向的地址的克隆`IHostSecurityContext`要捕获的对象。</span><span class="sxs-lookup"><span data-stu-id="dbddd-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbddd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="dbddd-107">Return Value</span></span>  
  
|<span data-ttu-id="dbddd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbddd-108">HRESULT</span></span>|<span data-ttu-id="dbddd-109">描述</span><span class="sxs-lookup"><span data-stu-id="dbddd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbddd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbddd-110">S_OK</span></span>|<span data-ttu-id="dbddd-111">`Capture` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="dbddd-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="dbddd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dbddd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dbddd-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="dbddd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dbddd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dbddd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dbddd-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="dbddd-115">The call timed out.</span></span>|  
|<span data-ttu-id="dbddd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dbddd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dbddd-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="dbddd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dbddd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dbddd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dbddd-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="dbddd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dbddd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbddd-120">E_FAIL</span></span>|<span data-ttu-id="dbddd-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="dbddd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dbddd-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="dbddd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dbddd-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="dbddd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbddd-124">备注</span><span class="sxs-lookup"><span data-stu-id="dbddd-124">Remarks</span></span>  
 <span data-ttu-id="dbddd-125">从返回的接口指针`Capture`是捕获的上下文的克隆。</span><span class="sxs-lookup"><span data-stu-id="dbddd-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="dbddd-126">此信息移动跨异步代码点后，其生存期分开，对其进行调用的指针。</span><span class="sxs-lookup"><span data-stu-id="dbddd-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="dbddd-127">因此可以释放原始指针。</span><span class="sxs-lookup"><span data-stu-id="dbddd-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbddd-128">要求</span><span class="sxs-lookup"><span data-stu-id="dbddd-128">Requirements</span></span>  
 <span data-ttu-id="dbddd-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbddd-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbddd-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dbddd-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbddd-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dbddd-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbddd-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbddd-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbddd-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbddd-133">See also</span></span>
- [<span data-ttu-id="dbddd-134">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="dbddd-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="dbddd-135">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="dbddd-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
