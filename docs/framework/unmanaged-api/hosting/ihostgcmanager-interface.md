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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 238b054d240437df64a83a9c4daad34d4bd5d36a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228871"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="d1fe3-102">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="d1fe3-102">IHostGCManager Interface</span></span>
<span data-ttu-id="d1fe3-103">提供方法，以通知宿主中的垃圾回收机制由公共语言运行时 (CLR) 实现的事件。</span><span class="sxs-lookup"><span data-stu-id="d1fe3-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="d1fe3-104">成员</span><span class="sxs-lookup"><span data-stu-id="d1fe3-104">Members</span></span>  
  
|<span data-ttu-id="d1fe3-105">成员</span><span class="sxs-lookup"><span data-stu-id="d1fe3-105">Member</span></span>|<span data-ttu-id="d1fe3-106">描述</span><span class="sxs-lookup"><span data-stu-id="d1fe3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1fe3-107">SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="d1fe3-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="d1fe3-108">通知宿主 CLR 继续执行过程中被挂起垃圾回收的线程上的任务。</span><span class="sxs-lookup"><span data-stu-id="d1fe3-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="d1fe3-109">SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="d1fe3-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="d1fe3-110">通知宿主 CLR 正在挂起任务，以执行垃圾回收的执行。</span><span class="sxs-lookup"><span data-stu-id="d1fe3-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="d1fe3-111">ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="d1fe3-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="d1fe3-112">通知主机发出方法调用的线程即将进行垃圾回收阻止。</span><span class="sxs-lookup"><span data-stu-id="d1fe3-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1fe3-113">要求</span><span class="sxs-lookup"><span data-stu-id="d1fe3-113">Requirements</span></span>  
 <span data-ttu-id="d1fe3-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1fe3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1fe3-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d1fe3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1fe3-116">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d1fe3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d1fe3-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d1fe3-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1fe3-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1fe3-118">See also</span></span>

- [<span data-ttu-id="d1fe3-119">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="d1fe3-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d1fe3-120">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d1fe3-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d1fe3-121">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="d1fe3-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d1fe3-122">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d1fe3-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="d1fe3-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="d1fe3-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
