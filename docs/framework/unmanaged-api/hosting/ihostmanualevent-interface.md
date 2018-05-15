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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53aaf4c23861666962e5567a6cf9eb9fffc6292f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="dbd8f-102">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="dbd8f-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="dbd8f-103">提供的表示形式的手动重置事件主机的实现。</span><span class="sxs-lookup"><span data-stu-id="dbd8f-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dbd8f-104">方法</span><span class="sxs-lookup"><span data-stu-id="dbd8f-104">Methods</span></span>  
  
|<span data-ttu-id="dbd8f-105">方法</span><span class="sxs-lookup"><span data-stu-id="dbd8f-105">Method</span></span>|<span data-ttu-id="dbd8f-106">描述</span><span class="sxs-lookup"><span data-stu-id="dbd8f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dbd8f-107">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="dbd8f-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="dbd8f-108">重置当前`IHostManualEvent`为非终止状态的实例。</span><span class="sxs-lookup"><span data-stu-id="dbd8f-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="dbd8f-109">Set 方法</span><span class="sxs-lookup"><span data-stu-id="dbd8f-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="dbd8f-110">设置当前`IHostManualEvent`发送信号状态的实例。</span><span class="sxs-lookup"><span data-stu-id="dbd8f-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="dbd8f-111">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="dbd8f-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="dbd8f-112">导致当前`IHostManualEvent`等待，直到其拥有的实例或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="dbd8f-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dbd8f-113">要求</span><span class="sxs-lookup"><span data-stu-id="dbd8f-113">Requirements</span></span>  
 <span data-ttu-id="dbd8f-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd8f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbd8f-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dbd8f-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbd8f-116">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dbd8f-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbd8f-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbd8f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd8f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbd8f-118">See Also</span></span>  
 [<span data-ttu-id="dbd8f-119">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="dbd8f-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="dbd8f-120">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="dbd8f-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="dbd8f-121">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="dbd8f-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="dbd8f-122">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="dbd8f-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="dbd8f-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="dbd8f-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
