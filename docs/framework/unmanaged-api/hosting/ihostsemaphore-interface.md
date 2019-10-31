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
ms.openlocfilehash: 2cf490bcd167b7a498ae21f479f616694ccb5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139476"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="70d8f-102">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="70d8f-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="70d8f-103">表示线程的信号量的主机实现。</span><span class="sxs-lookup"><span data-stu-id="70d8f-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70d8f-104">方法</span><span class="sxs-lookup"><span data-stu-id="70d8f-104">Methods</span></span>  
  
|<span data-ttu-id="70d8f-105">方法</span><span class="sxs-lookup"><span data-stu-id="70d8f-105">Method</span></span>|<span data-ttu-id="70d8f-106">描述</span><span class="sxs-lookup"><span data-stu-id="70d8f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70d8f-107">ReleaseSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="70d8f-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="70d8f-108">按指定量增加当前 `IHostSemaphore` 实例的计数。</span><span class="sxs-lookup"><span data-stu-id="70d8f-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="70d8f-109">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="70d8f-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="70d8f-110">导致当前 `IHostSemaphore` 实例等待，直到其拥有或经过指定的时间量。</span><span class="sxs-lookup"><span data-stu-id="70d8f-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70d8f-111">要求</span><span class="sxs-lookup"><span data-stu-id="70d8f-111">Requirements</span></span>  
 <span data-ttu-id="70d8f-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70d8f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70d8f-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="70d8f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70d8f-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="70d8f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70d8f-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70d8f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d8f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="70d8f-116">See also</span></span>

- [<span data-ttu-id="70d8f-117">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="70d8f-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="70d8f-118">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="70d8f-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="70d8f-119">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="70d8f-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="70d8f-120">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="70d8f-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="70d8f-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="70d8f-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
