---
title: ICLRMemoryNotificationCallback::OnMemoryNotification 方法
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
ms.openlocfilehash: 11b9b500e16917498856888c437c58c0df2edafb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140983"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="294f0-102">ICLRMemoryNotificationCallback::OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="294f0-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="294f0-103">向公共语言运行时（CLR）通知计算机上的内存负载。</span><span class="sxs-lookup"><span data-stu-id="294f0-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="294f0-104">语法</span><span class="sxs-lookup"><span data-stu-id="294f0-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="294f0-105">参数</span><span class="sxs-lookup"><span data-stu-id="294f0-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="294f0-106">中[EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)值之一，指示计算机当前遇到的内存压力。</span><span class="sxs-lookup"><span data-stu-id="294f0-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="294f0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="294f0-107">Return Value</span></span>  
  
|<span data-ttu-id="294f0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="294f0-108">HRESULT</span></span>|<span data-ttu-id="294f0-109">描述</span><span class="sxs-lookup"><span data-stu-id="294f0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="294f0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="294f0-110">S_OK</span></span>|<span data-ttu-id="294f0-111">`OnMemoryNotification` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="294f0-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="294f0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="294f0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="294f0-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="294f0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="294f0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="294f0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="294f0-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="294f0-115">The call timed out.</span></span>|  
|<span data-ttu-id="294f0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="294f0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="294f0-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="294f0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="294f0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="294f0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="294f0-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="294f0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="294f0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="294f0-120">E_FAIL</span></span>|<span data-ttu-id="294f0-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="294f0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="294f0-122">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="294f0-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="294f0-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="294f0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="294f0-124">备注</span><span class="sxs-lookup"><span data-stu-id="294f0-124">Remarks</span></span>  
 <span data-ttu-id="294f0-125">CLR 使用对[IHostMemoryManager：： RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)方法的调用向 `OnMemoryNotification` 注册回调。</span><span class="sxs-lookup"><span data-stu-id="294f0-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="294f0-126">当主机报告内存资源不足时，运行时将使用在回调中返回的信息来释放额外内存。</span><span class="sxs-lookup"><span data-stu-id="294f0-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="294f0-127">对 `OnMemoryNotification` 的调用从不会阻止。</span><span class="sxs-lookup"><span data-stu-id="294f0-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="294f0-128">它们始终立即返回。</span><span class="sxs-lookup"><span data-stu-id="294f0-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="294f0-129">要求</span><span class="sxs-lookup"><span data-stu-id="294f0-129">Requirements</span></span>  
 <span data-ttu-id="294f0-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="294f0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="294f0-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="294f0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="294f0-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="294f0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="294f0-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="294f0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="294f0-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="294f0-134">See also</span></span>

- [<span data-ttu-id="294f0-135">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="294f0-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="294f0-136">RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="294f0-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="294f0-137">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="294f0-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
