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
ms.openlocfilehash: 2b191243ea03adcfecaadbd3a5871e1773b28bb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124453"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="05738-102">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="05738-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="05738-103">提供宿主自动重置事件的实现的表示形式。</span><span class="sxs-lookup"><span data-stu-id="05738-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05738-104">方法</span><span class="sxs-lookup"><span data-stu-id="05738-104">Methods</span></span>  
  
|<span data-ttu-id="05738-105">方法</span><span class="sxs-lookup"><span data-stu-id="05738-105">Method</span></span>|<span data-ttu-id="05738-106">描述</span><span class="sxs-lookup"><span data-stu-id="05738-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05738-107">Set 方法</span><span class="sxs-lookup"><span data-stu-id="05738-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="05738-108">将当前 `IHostAutoEvent` 实例设置为终止状态。</span><span class="sxs-lookup"><span data-stu-id="05738-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="05738-109">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="05738-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="05738-110">导致当前 `IHostAutoEvent` 实例等待，直到事件拥有或经过指定的时间量。</span><span class="sxs-lookup"><span data-stu-id="05738-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05738-111">要求</span><span class="sxs-lookup"><span data-stu-id="05738-111">Requirements</span></span>  
 <span data-ttu-id="05738-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05738-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05738-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="05738-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05738-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="05738-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05738-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05738-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05738-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="05738-116">See also</span></span>

- [<span data-ttu-id="05738-117">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="05738-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="05738-118">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="05738-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="05738-119">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="05738-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="05738-120">承载接口</span><span class="sxs-lookup"><span data-stu-id="05738-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
