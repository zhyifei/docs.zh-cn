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
ms.openlocfilehash: 88f2ef8299911905d651ad5c3076dc9c74f397f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438914"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="23397-102">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="23397-102">IHostCrst Interface</span></span>
<span data-ttu-id="23397-103">用作主机的表示形式的线程处理关键部分。</span><span class="sxs-lookup"><span data-stu-id="23397-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23397-104">方法</span><span class="sxs-lookup"><span data-stu-id="23397-104">Methods</span></span>  
  
|<span data-ttu-id="23397-105">方法</span><span class="sxs-lookup"><span data-stu-id="23397-105">Method</span></span>|<span data-ttu-id="23397-106">描述</span><span class="sxs-lookup"><span data-stu-id="23397-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23397-107">Enter 方法</span><span class="sxs-lookup"><span data-stu-id="23397-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="23397-108">进入临界区。</span><span class="sxs-lookup"><span data-stu-id="23397-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="23397-109">Leave 方法</span><span class="sxs-lookup"><span data-stu-id="23397-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="23397-110">离开临界区。</span><span class="sxs-lookup"><span data-stu-id="23397-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="23397-111">SetSpinCount 方法</span><span class="sxs-lookup"><span data-stu-id="23397-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="23397-112">设置临界区的重试次数。</span><span class="sxs-lookup"><span data-stu-id="23397-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="23397-113">TryEnter 方法</span><span class="sxs-lookup"><span data-stu-id="23397-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="23397-114">若要立即输入关键部分中，以及报告是成功还是失败的尝试。</span><span class="sxs-lookup"><span data-stu-id="23397-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23397-115">备注</span><span class="sxs-lookup"><span data-stu-id="23397-115">Remarks</span></span>  
 <span data-ttu-id="23397-116">`IHostCrst` 允许公共语言运行时 (CLR) 与主机的表示形式关键部分，直接进行通信，而不是如使用 Win32 函数`EnterCriticalSection`或`LeaveCriticalSection`。</span><span class="sxs-lookup"><span data-stu-id="23397-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23397-117">要求</span><span class="sxs-lookup"><span data-stu-id="23397-117">Requirements</span></span>  
 <span data-ttu-id="23397-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23397-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23397-119">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23397-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23397-120">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="23397-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23397-121">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23397-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23397-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="23397-122">See Also</span></span>  
 [<span data-ttu-id="23397-123">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="23397-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="23397-124">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="23397-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="23397-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="23397-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
