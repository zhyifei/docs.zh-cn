---
title: IHostManualEvent 接口
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 8eba189d6dfca3781c28631a72a9af3c037efeda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136786"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="19ea1-102">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="19ea1-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="19ea1-103">提供宿主手动重置事件表示形式的实现。</span><span class="sxs-lookup"><span data-stu-id="19ea1-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19ea1-104">方法</span><span class="sxs-lookup"><span data-stu-id="19ea1-104">Methods</span></span>  
  
|<span data-ttu-id="19ea1-105">方法</span><span class="sxs-lookup"><span data-stu-id="19ea1-105">Method</span></span>|<span data-ttu-id="19ea1-106">描述</span><span class="sxs-lookup"><span data-stu-id="19ea1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19ea1-107">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="19ea1-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="19ea1-108">将当前 `IHostManualEvent` 实例重置为非终止状态。</span><span class="sxs-lookup"><span data-stu-id="19ea1-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="19ea1-109">Set 方法</span><span class="sxs-lookup"><span data-stu-id="19ea1-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="19ea1-110">将当前 `IHostManualEvent` 实例设置为终止状态。</span><span class="sxs-lookup"><span data-stu-id="19ea1-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="19ea1-111">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="19ea1-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="19ea1-112">导致当前 `IHostManualEvent` 实例等待，直到其拥有或经过指定的时间量。</span><span class="sxs-lookup"><span data-stu-id="19ea1-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19ea1-113">要求</span><span class="sxs-lookup"><span data-stu-id="19ea1-113">Requirements</span></span>  
 <span data-ttu-id="19ea1-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19ea1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19ea1-115">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="19ea1-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19ea1-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="19ea1-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19ea1-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19ea1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ea1-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="19ea1-118">See also</span></span>

- [<span data-ttu-id="19ea1-119">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="19ea1-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="19ea1-120">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="19ea1-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="19ea1-121">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="19ea1-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="19ea1-122">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="19ea1-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="19ea1-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="19ea1-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
