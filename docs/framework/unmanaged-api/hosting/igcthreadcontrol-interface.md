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
ms.openlocfilehash: 78e667acf1573769a1a67b4c964d7801f11838fe
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805132"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="78a73-102">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="78a73-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="78a73-103">提供一些方法，这些方法用于参与要阻止垃圾回收的线程的计划。</span><span class="sxs-lookup"><span data-stu-id="78a73-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78a73-104">方法</span><span class="sxs-lookup"><span data-stu-id="78a73-104">Methods</span></span>  
  
|<span data-ttu-id="78a73-105">方法</span><span class="sxs-lookup"><span data-stu-id="78a73-105">Method</span></span>|<span data-ttu-id="78a73-106">说明</span><span class="sxs-lookup"><span data-stu-id="78a73-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="78a73-107">SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="78a73-107">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="78a73-108">向宿主通知运行时在垃圾回收或其他挂起后正在恢复线程。</span><span class="sxs-lookup"><span data-stu-id="78a73-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="78a73-109">SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="78a73-109">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="78a73-110">通知宿主运行时正在为垃圾回收或其他挂起开始线程挂起。</span><span class="sxs-lookup"><span data-stu-id="78a73-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="78a73-111">ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="78a73-111">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="78a73-112">通知宿主发出调用的线程将要阻止，可能用于垃圾回收或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="78a73-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78a73-113">要求</span><span class="sxs-lookup"><span data-stu-id="78a73-113">Requirements</span></span>  
 <span data-ttu-id="78a73-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="78a73-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78a73-115">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="78a73-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78a73-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="78a73-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78a73-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78a73-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a73-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78a73-118">See also</span></span>

- [<span data-ttu-id="78a73-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="78a73-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
