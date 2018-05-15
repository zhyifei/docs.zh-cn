---
title: IGCThreadControl 接口
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9296aedf24979624c3d7357a4d51be835716a16f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="7d1ab-102">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="7d1ab-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="7d1ab-103">提供用于参与否则会阻止垃圾回收的线程调度的方法。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d1ab-104">方法</span><span class="sxs-lookup"><span data-stu-id="7d1ab-104">Methods</span></span>  
  
|<span data-ttu-id="7d1ab-105">方法</span><span class="sxs-lookup"><span data-stu-id="7d1ab-105">Method</span></span>|<span data-ttu-id="7d1ab-106">描述</span><span class="sxs-lookup"><span data-stu-id="7d1ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d1ab-107">SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="7d1ab-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="7d1ab-108">通知主机运行时正在恢复后垃圾回收或其他挂起的线程。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="7d1ab-109">SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="7d1ab-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="7d1ab-110">通知主机运行时正在开始垃圾回收的线程挂起或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="7d1ab-111">ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="7d1ab-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="7d1ab-112">通知主机执行调用的线程即将进行阻止，可能针对垃圾回收或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d1ab-113">要求</span><span class="sxs-lookup"><span data-stu-id="7d1ab-113">Requirements</span></span>  
 <span data-ttu-id="7d1ab-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d1ab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d1ab-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d1ab-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d1ab-116">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7d1ab-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d1ab-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d1ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1ab-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d1ab-118">See Also</span></span>  
 [<span data-ttu-id="7d1ab-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="7d1ab-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
