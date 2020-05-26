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
ms.openlocfilehash: 428e4cf8997713b08e40d9376c34ae5eee8cfa32
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804857"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="b48f2-102">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="b48f2-102">IHostGCManager Interface</span></span>
<span data-ttu-id="b48f2-103">提供一些方法，这些方法用于通知由公共语言运行时（CLR）实现的垃圾回收机制中的事件宿主。</span><span class="sxs-lookup"><span data-stu-id="b48f2-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="b48f2-104">成员</span><span class="sxs-lookup"><span data-stu-id="b48f2-104">Members</span></span>  
  
|<span data-ttu-id="b48f2-105">成员</span><span class="sxs-lookup"><span data-stu-id="b48f2-105">Member</span></span>|<span data-ttu-id="b48f2-106">描述</span><span class="sxs-lookup"><span data-stu-id="b48f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b48f2-107">SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="b48f2-107">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="b48f2-108">通知宿主 CLR 正在继续执行已挂起垃圾回收的线程上的任务。</span><span class="sxs-lookup"><span data-stu-id="b48f2-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="b48f2-109">SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="b48f2-109">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="b48f2-110">通知宿主 CLR 正在暂停执行任务，以执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b48f2-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="b48f2-111">ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="b48f2-111">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="b48f2-112">通知宿主从中发出方法调用的线程将要阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b48f2-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b48f2-113">要求</span><span class="sxs-lookup"><span data-stu-id="b48f2-113">Requirements</span></span>  
 <span data-ttu-id="b48f2-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b48f2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b48f2-115">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b48f2-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b48f2-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b48f2-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b48f2-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b48f2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b48f2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b48f2-118">See also</span></span>

- [<span data-ttu-id="b48f2-119">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="b48f2-119">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b48f2-120">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b48f2-120">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b48f2-121">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="b48f2-121">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b48f2-122">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b48f2-122">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="b48f2-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="b48f2-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
