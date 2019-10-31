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
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130529"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="e38f3-102">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="e38f3-102">IHostCrst Interface</span></span>
<span data-ttu-id="e38f3-103">用作线程的关键部分的宿主表示形式。</span><span class="sxs-lookup"><span data-stu-id="e38f3-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e38f3-104">方法</span><span class="sxs-lookup"><span data-stu-id="e38f3-104">Methods</span></span>  
  
|<span data-ttu-id="e38f3-105">方法</span><span class="sxs-lookup"><span data-stu-id="e38f3-105">Method</span></span>|<span data-ttu-id="e38f3-106">描述</span><span class="sxs-lookup"><span data-stu-id="e38f3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e38f3-107">Enter 方法</span><span class="sxs-lookup"><span data-stu-id="e38f3-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="e38f3-108">输入临界区。</span><span class="sxs-lookup"><span data-stu-id="e38f3-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="e38f3-109">Leave 方法</span><span class="sxs-lookup"><span data-stu-id="e38f3-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="e38f3-110">离开临界区。</span><span class="sxs-lookup"><span data-stu-id="e38f3-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="e38f3-111">SetSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="e38f3-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="e38f3-112">设置临界区的旋转计数。</span><span class="sxs-lookup"><span data-stu-id="e38f3-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="e38f3-113">TryEnter 方法</span><span class="sxs-lookup"><span data-stu-id="e38f3-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="e38f3-114">尝试输入临界区，并立即报告成功或失败。</span><span class="sxs-lookup"><span data-stu-id="e38f3-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e38f3-115">备注</span><span class="sxs-lookup"><span data-stu-id="e38f3-115">Remarks</span></span>  
 <span data-ttu-id="e38f3-116">`IHostCrst` 允许公共语言运行时（CLR）与关键节的主机表示形式直接通信，而不是使用 `EnterCriticalSection` 或 `LeaveCriticalSection`等 Win32 函数。</span><span class="sxs-lookup"><span data-stu-id="e38f3-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e38f3-117">要求</span><span class="sxs-lookup"><span data-stu-id="e38f3-117">Requirements</span></span>  
 <span data-ttu-id="e38f3-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e38f3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e38f3-119">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e38f3-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e38f3-120">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e38f3-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e38f3-121">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e38f3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e38f3-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e38f3-122">See also</span></span>

- [<span data-ttu-id="e38f3-123">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="e38f3-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="e38f3-124">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="e38f3-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="e38f3-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="e38f3-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
