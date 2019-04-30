---
title: IHostCrst 接口
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 939f100e8ee386642a29c33827a8339caf0467b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967825"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="19527-102">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="19527-102">IHostCrst Interface</span></span>
<span data-ttu-id="19527-103">用作主机的临界区对线程处理的表示形式。</span><span class="sxs-lookup"><span data-stu-id="19527-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19527-104">方法</span><span class="sxs-lookup"><span data-stu-id="19527-104">Methods</span></span>  
  
|<span data-ttu-id="19527-105">方法</span><span class="sxs-lookup"><span data-stu-id="19527-105">Method</span></span>|<span data-ttu-id="19527-106">描述</span><span class="sxs-lookup"><span data-stu-id="19527-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19527-107">Enter 方法</span><span class="sxs-lookup"><span data-stu-id="19527-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="19527-108">将进入关键节。</span><span class="sxs-lookup"><span data-stu-id="19527-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="19527-109">Leave 方法</span><span class="sxs-lookup"><span data-stu-id="19527-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="19527-110">离开临界区。</span><span class="sxs-lookup"><span data-stu-id="19527-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="19527-111">SetSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="19527-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="19527-112">设置临界区旋转计数。</span><span class="sxs-lookup"><span data-stu-id="19527-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="19527-113">TryEnter 方法</span><span class="sxs-lookup"><span data-stu-id="19527-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="19527-114">若要立即输入的关键部分，并报告成功或失败的尝试。</span><span class="sxs-lookup"><span data-stu-id="19527-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19527-115">备注</span><span class="sxs-lookup"><span data-stu-id="19527-115">Remarks</span></span>  
 <span data-ttu-id="19527-116">`IHostCrst` 允许公共语言运行时 (CLR) 与主机的关键部分的表示形式直接进行通信，而不是使用 Win32 函数类似于`EnterCriticalSection`或`LeaveCriticalSection`。</span><span class="sxs-lookup"><span data-stu-id="19527-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19527-117">要求</span><span class="sxs-lookup"><span data-stu-id="19527-117">Requirements</span></span>  
 <span data-ttu-id="19527-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19527-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19527-119">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19527-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19527-120">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="19527-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19527-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19527-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19527-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="19527-122">See also</span></span>

- [<span data-ttu-id="19527-123">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="19527-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="19527-124">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="19527-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="19527-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="19527-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
