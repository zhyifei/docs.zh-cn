---
title: "IHostSemaphore 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSemaphore
helpviewer_keywords: IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bcc6a9a7847932e9e469cdbffc9792e1d5860570
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="e91f3-102">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="e91f3-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="e91f3-103">表示用于线程处理的信号量的主机的实现。</span><span class="sxs-lookup"><span data-stu-id="e91f3-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e91f3-104">方法</span><span class="sxs-lookup"><span data-stu-id="e91f3-104">Methods</span></span>  
  
|<span data-ttu-id="e91f3-105">方法</span><span class="sxs-lookup"><span data-stu-id="e91f3-105">Method</span></span>|<span data-ttu-id="e91f3-106">描述</span><span class="sxs-lookup"><span data-stu-id="e91f3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e91f3-107">ReleaseSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="e91f3-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="e91f3-108">当前的计数增加`IHostSemaphore`指定的量的实例。</span><span class="sxs-lookup"><span data-stu-id="e91f3-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="e91f3-109">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="e91f3-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="e91f3-110">导致当前`IHostSemaphore`要等待，直到它拥有实例或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="e91f3-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e91f3-111">惠?</span><span class="sxs-lookup"><span data-stu-id="e91f3-111">Requirements</span></span>  
 <span data-ttu-id="e91f3-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e91f3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e91f3-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e91f3-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e91f3-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e91f3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e91f3-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e91f3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91f3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e91f3-116">See Also</span></span>  
 [<span data-ttu-id="e91f3-117">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="e91f3-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e91f3-118">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="e91f3-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="e91f3-119">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="e91f3-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="e91f3-120">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="e91f3-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="e91f3-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="e91f3-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
