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
ms.openlocfilehash: c8b4d4c7edec47ab4acaae2a5cd93ad474612063
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855541"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="b017c-102">IHostSecurityContext::Capture 方法</span><span class="sxs-lookup"><span data-stu-id="b017c-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="b017c-103">获取通过调用[IHostSecurityManager：： GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)返回的[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)实例的克隆。</span><span class="sxs-lookup"><span data-stu-id="b017c-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b017c-104">语法</span><span class="sxs-lookup"><span data-stu-id="b017c-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b017c-105">参数</span><span class="sxs-lookup"><span data-stu-id="b017c-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="b017c-106">弄一个指针，指向要捕获的`IHostSecurityContext`对象的克隆地址。</span><span class="sxs-lookup"><span data-stu-id="b017c-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b017c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b017c-107">Return Value</span></span>  
  
|<span data-ttu-id="b017c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b017c-108">HRESULT</span></span>|<span data-ttu-id="b017c-109">描述</span><span class="sxs-lookup"><span data-stu-id="b017c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b017c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b017c-110">S_OK</span></span>|<span data-ttu-id="b017c-111">`Capture`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b017c-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="b017c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b017c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b017c-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b017c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b017c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b017c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b017c-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="b017c-115">The call timed out.</span></span>|  
|<span data-ttu-id="b017c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b017c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b017c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b017c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b017c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b017c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b017c-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="b017c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b017c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b017c-120">E_FAIL</span></span>|<span data-ttu-id="b017c-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b017c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b017c-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b017c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b017c-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b017c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b017c-124">备注</span><span class="sxs-lookup"><span data-stu-id="b017c-124">Remarks</span></span>  
 <span data-ttu-id="b017c-125">从`Capture`返回的接口指针是捕获上下文的克隆。</span><span class="sxs-lookup"><span data-stu-id="b017c-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="b017c-126">在异步代码点上移动此信息时，其生存期与进行调用的指针的生存期分开。</span><span class="sxs-lookup"><span data-stu-id="b017c-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="b017c-127">因此，可以释放原始指针。</span><span class="sxs-lookup"><span data-stu-id="b017c-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b017c-128">要求</span><span class="sxs-lookup"><span data-stu-id="b017c-128">Requirements</span></span>  
 <span data-ttu-id="b017c-129">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b017c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b017c-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b017c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b017c-131">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b017c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b017c-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b017c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b017c-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="b017c-133">See also</span></span>

- [<span data-ttu-id="b017c-134">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="b017c-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="b017c-135">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="b017c-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
