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
ms.openlocfilehash: eb09422872a0d9565be286c25ca1b28d1c45e08f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501693"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="10a43-102">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="10a43-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="10a43-103">提供的手动重置事件的表示形式的主机的实现。</span><span class="sxs-lookup"><span data-stu-id="10a43-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10a43-104">方法</span><span class="sxs-lookup"><span data-stu-id="10a43-104">Methods</span></span>  
  
|<span data-ttu-id="10a43-105">方法</span><span class="sxs-lookup"><span data-stu-id="10a43-105">Method</span></span>|<span data-ttu-id="10a43-106">描述</span><span class="sxs-lookup"><span data-stu-id="10a43-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10a43-107">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="10a43-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="10a43-108">重置当前`IHostManualEvent`为非终止状态的实例。</span><span class="sxs-lookup"><span data-stu-id="10a43-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="10a43-109">Set 方法</span><span class="sxs-lookup"><span data-stu-id="10a43-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="10a43-110">设置当前`IHostManualEvent`到已发出信号状态的实例。</span><span class="sxs-lookup"><span data-stu-id="10a43-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="10a43-111">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="10a43-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="10a43-112">导致当前`IHostManualEvent`实例等待，直到拥有它或指定的经历的时间量。</span><span class="sxs-lookup"><span data-stu-id="10a43-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10a43-113">要求</span><span class="sxs-lookup"><span data-stu-id="10a43-113">Requirements</span></span>  
 <span data-ttu-id="10a43-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10a43-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a43-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10a43-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10a43-116">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="10a43-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10a43-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a43-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a43-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="10a43-118">See also</span></span>
- [<span data-ttu-id="10a43-119">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="10a43-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="10a43-120">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="10a43-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="10a43-121">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="10a43-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="10a43-122">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="10a43-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="10a43-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="10a43-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
