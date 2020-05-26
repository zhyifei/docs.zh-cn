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
ms.openlocfilehash: 8345d85502087568cb05dd262cccf181e3ca07ac
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803690"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="ddb0f-102">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="ddb0f-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="ddb0f-103">表示线程的信号量的主机实现。</span><span class="sxs-lookup"><span data-stu-id="ddb0f-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ddb0f-104">方法</span><span class="sxs-lookup"><span data-stu-id="ddb0f-104">Methods</span></span>  
  
|<span data-ttu-id="ddb0f-105">方法</span><span class="sxs-lookup"><span data-stu-id="ddb0f-105">Method</span></span>|<span data-ttu-id="ddb0f-106">说明</span><span class="sxs-lookup"><span data-stu-id="ddb0f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ddb0f-107">ReleaseSemaphore 方法</span><span class="sxs-lookup"><span data-stu-id="ddb0f-107">ReleaseSemaphore Method</span></span>](ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="ddb0f-108">`IHostSemaphore`按指定量增加当前实例的计数。</span><span class="sxs-lookup"><span data-stu-id="ddb0f-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="ddb0f-109">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="ddb0f-109">Wait Method</span></span>](ihostsemaphore-wait-method.md)|<span data-ttu-id="ddb0f-110">使当前 `IHostSemaphore` 实例等待，直到其拥有或经过指定的时间量。</span><span class="sxs-lookup"><span data-stu-id="ddb0f-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddb0f-111">要求</span><span class="sxs-lookup"><span data-stu-id="ddb0f-111">Requirements</span></span>  
 <span data-ttu-id="ddb0f-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddb0f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddb0f-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ddb0f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ddb0f-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ddb0f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddb0f-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddb0f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb0f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddb0f-116">See also</span></span>

- [<span data-ttu-id="ddb0f-117">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="ddb0f-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="ddb0f-118">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="ddb0f-118">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="ddb0f-119">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="ddb0f-119">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="ddb0f-120">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="ddb0f-120">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="ddb0f-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="ddb0f-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
