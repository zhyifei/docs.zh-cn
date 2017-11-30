---
title: "IHostManualEvent 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent
helpviewer_keywords: IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c19125d96d5f4a9e91fc083d53f36ebebd2c569
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="a26d2-102">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="a26d2-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="a26d2-103">提供的表示形式的手动重置事件主机的实现。</span><span class="sxs-lookup"><span data-stu-id="a26d2-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a26d2-104">方法</span><span class="sxs-lookup"><span data-stu-id="a26d2-104">Methods</span></span>  
  
|<span data-ttu-id="a26d2-105">方法</span><span class="sxs-lookup"><span data-stu-id="a26d2-105">Method</span></span>|<span data-ttu-id="a26d2-106">描述</span><span class="sxs-lookup"><span data-stu-id="a26d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a26d2-107">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="a26d2-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="a26d2-108">重置当前`IHostManualEvent`为非终止状态的实例。</span><span class="sxs-lookup"><span data-stu-id="a26d2-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="a26d2-109">Set 方法</span><span class="sxs-lookup"><span data-stu-id="a26d2-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="a26d2-110">设置当前`IHostManualEvent`发送信号状态的实例。</span><span class="sxs-lookup"><span data-stu-id="a26d2-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="a26d2-111">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="a26d2-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="a26d2-112">导致当前`IHostManualEvent`等待，直到其拥有的实例或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="a26d2-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a26d2-113">要求</span><span class="sxs-lookup"><span data-stu-id="a26d2-113">Requirements</span></span>  
 <span data-ttu-id="a26d2-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a26d2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a26d2-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a26d2-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a26d2-116">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a26d2-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a26d2-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a26d2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a26d2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a26d2-118">See Also</span></span>  
 [<span data-ttu-id="a26d2-119">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="a26d2-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="a26d2-120">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="a26d2-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="a26d2-121">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="a26d2-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="a26d2-122">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="a26d2-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="a26d2-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="a26d2-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
