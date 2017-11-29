---
title: "IHostGCManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager
helpviewer_keywords: IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0927b236af094b964261a9b2a49a33d1ea2b9391
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="3bfb2-102">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="3bfb2-102">IHostGCManager Interface</span></span>
<span data-ttu-id="3bfb2-103">提供通知宿主的垃圾回收机制实现的公共语言运行时 (CLR) 中的事件的方法。</span><span class="sxs-lookup"><span data-stu-id="3bfb2-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="3bfb2-104">成员</span><span class="sxs-lookup"><span data-stu-id="3bfb2-104">Members</span></span>  
  
|<span data-ttu-id="3bfb2-105">成员</span><span class="sxs-lookup"><span data-stu-id="3bfb2-105">Member</span></span>|<span data-ttu-id="3bfb2-106">描述</span><span class="sxs-lookup"><span data-stu-id="3bfb2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3bfb2-107">SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="3bfb2-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="3bfb2-108">通知主机 CLR 正在恢复已被挂起垃圾回收的线程上的任务的执行。</span><span class="sxs-lookup"><span data-stu-id="3bfb2-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="3bfb2-109">SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="3bfb2-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="3bfb2-110">通知主机 CLR 正处于挂起状态的任务，执行垃圾回收的执行。</span><span class="sxs-lookup"><span data-stu-id="3bfb2-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="3bfb2-111">ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="3bfb2-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="3bfb2-112">通知主机从中进行方法调用的线程即将阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3bfb2-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bfb2-113">要求</span><span class="sxs-lookup"><span data-stu-id="3bfb2-113">Requirements</span></span>  
 <span data-ttu-id="3bfb2-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3bfb2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bfb2-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3bfb2-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bfb2-116">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3bfb2-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bfb2-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bfb2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bfb2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bfb2-118">See Also</span></span>  
 [<span data-ttu-id="3bfb2-119">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="3bfb2-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3bfb2-120">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="3bfb2-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3bfb2-121">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="3bfb2-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="3bfb2-122">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="3bfb2-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="3bfb2-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="3bfb2-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
