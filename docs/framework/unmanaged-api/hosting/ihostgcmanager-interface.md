---
title: IHostGCManager 接口
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: 6f7158bcac7ad22647104e2041da959285d2be8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130484"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="2c676-102">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="2c676-102">IHostGCManager Interface</span></span>
<span data-ttu-id="2c676-103">提供一些方法，这些方法用于通知由公共语言运行时（CLR）实现的垃圾回收机制中的事件宿主。</span><span class="sxs-lookup"><span data-stu-id="2c676-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="2c676-104">Members</span><span class="sxs-lookup"><span data-stu-id="2c676-104">Members</span></span>  
  
|<span data-ttu-id="2c676-105">成员</span><span class="sxs-lookup"><span data-stu-id="2c676-105">Member</span></span>|<span data-ttu-id="2c676-106">描述</span><span class="sxs-lookup"><span data-stu-id="2c676-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c676-107">SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="2c676-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="2c676-108">通知宿主 CLR 正在继续执行已挂起垃圾回收的线程上的任务。</span><span class="sxs-lookup"><span data-stu-id="2c676-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="2c676-109">SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="2c676-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="2c676-110">通知宿主 CLR 正在暂停执行任务，以执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2c676-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="2c676-111">ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="2c676-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="2c676-112">通知宿主从中发出方法调用的线程将要阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2c676-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c676-113">要求</span><span class="sxs-lookup"><span data-stu-id="2c676-113">Requirements</span></span>  
 <span data-ttu-id="2c676-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c676-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c676-115">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2c676-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c676-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="2c676-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c676-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c676-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c676-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c676-118">See also</span></span>

- [<span data-ttu-id="2c676-119">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="2c676-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2c676-120">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2c676-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2c676-121">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="2c676-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2c676-122">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2c676-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="2c676-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="2c676-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
