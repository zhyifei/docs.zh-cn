---
title: IHostAutoEvent 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7f2b65f263256fe887c61c7b866beaa0038c37d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437409"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="14cf6-102">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="14cf6-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="14cf6-103">提供的表示形式的自动重置事件的主机的实现。</span><span class="sxs-lookup"><span data-stu-id="14cf6-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14cf6-104">方法</span><span class="sxs-lookup"><span data-stu-id="14cf6-104">Methods</span></span>  
  
|<span data-ttu-id="14cf6-105">方法</span><span class="sxs-lookup"><span data-stu-id="14cf6-105">Method</span></span>|<span data-ttu-id="14cf6-106">描述</span><span class="sxs-lookup"><span data-stu-id="14cf6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14cf6-107">Set 方法</span><span class="sxs-lookup"><span data-stu-id="14cf6-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="14cf6-108">设置当前`IHostAutoEvent`发送信号状态的实例。</span><span class="sxs-lookup"><span data-stu-id="14cf6-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="14cf6-109">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="14cf6-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="14cf6-110">导致当前`IHostAutoEvent`要等待，直到在拥有事件实例或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="14cf6-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14cf6-111">要求</span><span class="sxs-lookup"><span data-stu-id="14cf6-111">Requirements</span></span>  
 <span data-ttu-id="14cf6-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="14cf6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14cf6-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="14cf6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14cf6-114">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="14cf6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14cf6-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14cf6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14cf6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="14cf6-116">See Also</span></span>  
 [<span data-ttu-id="14cf6-117">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="14cf6-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="14cf6-118">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="14cf6-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="14cf6-119">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="14cf6-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="14cf6-120">承载接口</span><span class="sxs-lookup"><span data-stu-id="14cf6-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
