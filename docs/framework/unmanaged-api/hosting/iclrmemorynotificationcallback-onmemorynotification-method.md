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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 899d0cf6a0475846b749bd0b7cbda41b1b88253d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949707"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="3b2d6-102">ICLRMemoryNotificationCallback::OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="3b2d6-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="3b2d6-103">向公共语言运行时 (CLR) 通知计算机上的内存负载。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b2d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b2d6-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b2d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="3b2d6-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="3b2d6-106">中[EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)值之一, 指示计算机当前遇到的内存压力。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b2d6-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3b2d6-107">Return Value</span></span>  
  
|<span data-ttu-id="3b2d6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b2d6-108">HRESULT</span></span>|<span data-ttu-id="3b2d6-109">描述</span><span class="sxs-lookup"><span data-stu-id="3b2d6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b2d6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b2d6-110">S_OK</span></span>|<span data-ttu-id="3b2d6-111">`OnMemoryNotification`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="3b2d6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3b2d6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3b2d6-113">CLR 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3b2d6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3b2d6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3b2d6-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-115">The call timed out.</span></span>|  
|<span data-ttu-id="3b2d6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3b2d6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3b2d6-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3b2d6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3b2d6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3b2d6-119">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3b2d6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3b2d6-120">E_FAIL</span></span>|<span data-ttu-id="3b2d6-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3b2d6-122">方法返回 E_FAIL 后, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3b2d6-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b2d6-124">备注</span><span class="sxs-lookup"><span data-stu-id="3b2d6-124">Remarks</span></span>  
 <span data-ttu-id="3b2d6-125">CLR 使用对`OnMemoryNotification` [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)方法的调用向注册回调。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="3b2d6-126">当主机报告内存资源不足时, 运行时将使用在回调中返回的信息来释放额外内存。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b2d6-127">对`OnMemoryNotification`从不阻止的的调用。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="3b2d6-128">它们始终立即返回。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b2d6-129">要求</span><span class="sxs-lookup"><span data-stu-id="3b2d6-129">Requirements</span></span>  
 <span data-ttu-id="3b2d6-130">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b2d6-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b2d6-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3b2d6-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b2d6-132">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3b2d6-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b2d6-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b2d6-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b2d6-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b2d6-134">See also</span></span>

- [<span data-ttu-id="3b2d6-135">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="3b2d6-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="3b2d6-136">RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="3b2d6-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="3b2d6-137">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3b2d6-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
