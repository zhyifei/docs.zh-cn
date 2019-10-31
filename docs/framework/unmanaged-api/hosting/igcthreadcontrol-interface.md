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
ms.openlocfilehash: 3aba31f60af25144b9f01aa9ca8cc633d4c1a438
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134805"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="7718e-102">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="7718e-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="7718e-103">提供一些方法，这些方法用于参与要阻止垃圾回收的线程的计划。</span><span class="sxs-lookup"><span data-stu-id="7718e-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7718e-104">方法</span><span class="sxs-lookup"><span data-stu-id="7718e-104">Methods</span></span>  
  
|<span data-ttu-id="7718e-105">方法</span><span class="sxs-lookup"><span data-stu-id="7718e-105">Method</span></span>|<span data-ttu-id="7718e-106">描述</span><span class="sxs-lookup"><span data-stu-id="7718e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7718e-107">SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="7718e-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="7718e-108">向宿主通知运行时在垃圾回收或其他挂起后正在恢复线程。</span><span class="sxs-lookup"><span data-stu-id="7718e-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="7718e-109">SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="7718e-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="7718e-110">通知宿主运行时正在为垃圾回收或其他挂起开始线程挂起。</span><span class="sxs-lookup"><span data-stu-id="7718e-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="7718e-111">ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="7718e-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="7718e-112">通知宿主发出调用的线程将要阻止，可能用于垃圾回收或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="7718e-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7718e-113">要求</span><span class="sxs-lookup"><span data-stu-id="7718e-113">Requirements</span></span>  
 <span data-ttu-id="7718e-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7718e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7718e-115">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7718e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7718e-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7718e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7718e-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7718e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7718e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7718e-118">See also</span></span>

- [<span data-ttu-id="7718e-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="7718e-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
