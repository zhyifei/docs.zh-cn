---
title: "ICLRSyncManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager
helpviewer_keywords: ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1e47f02a5a84b909b03c6be4e0a43c7166a1ddc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="192b3-102">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="192b3-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="192b3-103">定义允许主机以获取有关请求的任务的信息并在其同步实现检测死锁的方法。</span><span class="sxs-lookup"><span data-stu-id="192b3-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="192b3-104">方法</span><span class="sxs-lookup"><span data-stu-id="192b3-104">Methods</span></span>  
  
|<span data-ttu-id="192b3-105">方法</span><span class="sxs-lookup"><span data-stu-id="192b3-105">Method</span></span>|<span data-ttu-id="192b3-106">描述</span><span class="sxs-lookup"><span data-stu-id="192b3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="192b3-107">CreateRWLockOwnerIterator 方法</span><span class="sxs-lookup"><span data-stu-id="192b3-107">CreateRWLockOwnerIterator Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="192b3-108">公共语言运行时 (CLR) 创建主机可用于确定的读取器 / 编写器锁等待的任务集的迭代器的请求。</span><span class="sxs-lookup"><span data-stu-id="192b3-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="192b3-109">DeleteRWLockOwnerIterator 方法</span><span class="sxs-lookup"><span data-stu-id="192b3-109">DeleteRWLockOwnerIterator Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="192b3-110">请求 CLR 销毁由调用的迭代器`CreateRWLockOwnerIterator`。</span><span class="sxs-lookup"><span data-stu-id="192b3-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="192b3-111">GetMonitorOwner 方法</span><span class="sxs-lookup"><span data-stu-id="192b3-111">GetMonitorOwner Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="192b3-112">获取拥有指定的监视器的任务。</span><span class="sxs-lookup"><span data-stu-id="192b3-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="192b3-113">GetRWLockOwnerNext 方法</span><span class="sxs-lookup"><span data-stu-id="192b3-113">GetRWLockOwnerNext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="192b3-114">获取在当前的读取器 / 编写器锁等待下一个任务。</span><span class="sxs-lookup"><span data-stu-id="192b3-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="192b3-115">要求</span><span class="sxs-lookup"><span data-stu-id="192b3-115">Requirements</span></span>  
 <span data-ttu-id="192b3-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="192b3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="192b3-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="192b3-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="192b3-118">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="192b3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="192b3-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="192b3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="192b3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="192b3-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="192b3-121">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="192b3-121">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="192b3-122">托管和非托管线程处理</span><span class="sxs-lookup"><span data-stu-id="192b3-122">Managed and Unmanaged Threading</span></span>](http://msdn.microsoft.com/en-us/db425c20-4b2f-4433-bf96-76071c7881e5)  
 [<span data-ttu-id="192b3-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="192b3-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
