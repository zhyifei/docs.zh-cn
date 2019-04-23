---
title: ICLRSyncManager 接口
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3e4affa363083ce55ac3764c26412a0d60ba3f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203088"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="edfa5-102">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="edfa5-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="edfa5-103">定义允许主机以获取有关请求的任务的信息并在其同步实现检测死锁的方法。</span><span class="sxs-lookup"><span data-stu-id="edfa5-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="edfa5-104">方法</span><span class="sxs-lookup"><span data-stu-id="edfa5-104">Methods</span></span>  
  
|<span data-ttu-id="edfa5-105">方法</span><span class="sxs-lookup"><span data-stu-id="edfa5-105">Method</span></span>|<span data-ttu-id="edfa5-106">描述</span><span class="sxs-lookup"><span data-stu-id="edfa5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="edfa5-107">CreateRWLockOwnerIterator 方法</span><span class="sxs-lookup"><span data-stu-id="edfa5-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="edfa5-108">公共语言运行时 (CLR) 创建主机，用于确定读取器 / 编写器锁等待的任务集的迭代器的请求。</span><span class="sxs-lookup"><span data-stu-id="edfa5-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="edfa5-109">DeleteRWLockOwnerIterator 方法</span><span class="sxs-lookup"><span data-stu-id="edfa5-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="edfa5-110">请求 CLR 销毁一个迭代器，通过调用创建`CreateRWLockOwnerIterator`。</span><span class="sxs-lookup"><span data-stu-id="edfa5-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="edfa5-111">GetMonitorOwner 方法</span><span class="sxs-lookup"><span data-stu-id="edfa5-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="edfa5-112">获取拥有指定的监视器的任务。</span><span class="sxs-lookup"><span data-stu-id="edfa5-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="edfa5-113">GetRWLockOwnerNext 方法</span><span class="sxs-lookup"><span data-stu-id="edfa5-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="edfa5-114">获取在当前的读取器 / 编写器锁等待下一个任务。</span><span class="sxs-lookup"><span data-stu-id="edfa5-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="edfa5-115">要求</span><span class="sxs-lookup"><span data-stu-id="edfa5-115">Requirements</span></span>  
 <span data-ttu-id="edfa5-116">**平台：** 请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="edfa5-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edfa5-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="edfa5-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="edfa5-118">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="edfa5-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edfa5-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edfa5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edfa5-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="edfa5-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="edfa5-121">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="edfa5-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="edfa5-122">[托管和非托管线程处理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="edfa5-122">[Managed and Unmanaged Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="edfa5-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="edfa5-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
