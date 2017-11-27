---
title: "IHostManualEvent::Set 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Set
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f093e1278e74553ed78445e0cb83127a219e622
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="868b7-102">IHostManualEvent::Set 方法</span><span class="sxs-lookup"><span data-stu-id="868b7-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="868b7-103">设置当前[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)发送信号状态的实例。</span><span class="sxs-lookup"><span data-stu-id="868b7-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="868b7-104">语法</span><span class="sxs-lookup"><span data-stu-id="868b7-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="868b7-105">返回值</span><span class="sxs-lookup"><span data-stu-id="868b7-105">Return Value</span></span>  
  
|<span data-ttu-id="868b7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="868b7-106">HRESULT</span></span>|<span data-ttu-id="868b7-107">描述</span><span class="sxs-lookup"><span data-stu-id="868b7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="868b7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="868b7-108">S_OK</span></span>|<span data-ttu-id="868b7-109">`Set`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="868b7-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="868b7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="868b7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="868b7-111">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="868b7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="868b7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="868b7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="868b7-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="868b7-113">The call timed out.</span></span>|  
|<span data-ttu-id="868b7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="868b7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="868b7-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="868b7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="868b7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="868b7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="868b7-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="868b7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="868b7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="868b7-118">E_FAIL</span></span>|<span data-ttu-id="868b7-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="868b7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="868b7-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="868b7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="868b7-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="868b7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="868b7-122">要求</span><span class="sxs-lookup"><span data-stu-id="868b7-122">Requirements</span></span>  
 <span data-ttu-id="868b7-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="868b7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="868b7-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="868b7-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="868b7-125">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="868b7-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="868b7-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="868b7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868b7-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="868b7-127">See Also</span></span>  
 [<span data-ttu-id="868b7-128">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="868b7-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="868b7-129">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="868b7-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="868b7-130">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="868b7-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="868b7-131">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="868b7-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="868b7-132">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="868b7-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
