---
title: IHostSemaphore 接口
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d7d4a295832a958fb6a8fe2e6c43a09135500d3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182281"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="65914-102">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="65914-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="65914-103">表示用于线程处理的信号量的主机的实现。</span><span class="sxs-lookup"><span data-stu-id="65914-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65914-104">方法</span><span class="sxs-lookup"><span data-stu-id="65914-104">Methods</span></span>  
  
|<span data-ttu-id="65914-105">方法</span><span class="sxs-lookup"><span data-stu-id="65914-105">Method</span></span>|<span data-ttu-id="65914-106">描述</span><span class="sxs-lookup"><span data-stu-id="65914-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65914-107">ReleaseSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="65914-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="65914-108">当前计数`IHostSemaphore`实例指定的量。</span><span class="sxs-lookup"><span data-stu-id="65914-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="65914-109">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="65914-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="65914-110">导致当前`IHostSemaphore`等待，直到它拥有的实例或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="65914-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65914-111">要求</span><span class="sxs-lookup"><span data-stu-id="65914-111">Requirements</span></span>  
 <span data-ttu-id="65914-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65914-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65914-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65914-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65914-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="65914-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="65914-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="65914-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="65914-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="65914-116">See also</span></span>

- [<span data-ttu-id="65914-117">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="65914-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="65914-118">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="65914-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="65914-119">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="65914-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="65914-120">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="65914-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="65914-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="65914-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
