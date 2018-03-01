---
title: "IHostAutoEvent 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 91e790cf7c97c0045535870c2d41d628f943a22d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="e7a7c-102">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="e7a7c-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="e7a7c-103">提供的表示形式的自动重置事件的主机的实现。</span><span class="sxs-lookup"><span data-stu-id="e7a7c-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7a7c-104">方法</span><span class="sxs-lookup"><span data-stu-id="e7a7c-104">Methods</span></span>  
  
|<span data-ttu-id="e7a7c-105">方法</span><span class="sxs-lookup"><span data-stu-id="e7a7c-105">Method</span></span>|<span data-ttu-id="e7a7c-106">描述</span><span class="sxs-lookup"><span data-stu-id="e7a7c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7a7c-107">Set 方法</span><span class="sxs-lookup"><span data-stu-id="e7a7c-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="e7a7c-108">设置当前`IHostAutoEvent`发送信号状态的实例。</span><span class="sxs-lookup"><span data-stu-id="e7a7c-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="e7a7c-109">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="e7a7c-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="e7a7c-110">导致当前`IHostAutoEvent`要等待，直到在拥有事件实例或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="e7a7c-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7a7c-111">惠?</span><span class="sxs-lookup"><span data-stu-id="e7a7c-111">Requirements</span></span>  
 <span data-ttu-id="e7a7c-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7a7c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7a7c-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7a7c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7a7c-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e7a7c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7a7c-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7a7c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a7c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7a7c-116">See Also</span></span>  
 [<span data-ttu-id="e7a7c-117">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="e7a7c-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e7a7c-118">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="e7a7c-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="e7a7c-119">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="e7a7c-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="e7a7c-120">承载接口</span><span class="sxs-lookup"><span data-stu-id="e7a7c-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
