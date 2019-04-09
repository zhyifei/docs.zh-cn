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
ms.openlocfilehash: 5c00f401bedc1a2810c4e9b3046a45e53a79f1ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134259"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="a7e99-102">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="a7e99-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="a7e99-103">提供用于参与防止因阻塞而垃圾回收的线程的调度方法。</span><span class="sxs-lookup"><span data-stu-id="a7e99-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7e99-104">方法</span><span class="sxs-lookup"><span data-stu-id="a7e99-104">Methods</span></span>  
  
|<span data-ttu-id="a7e99-105">方法</span><span class="sxs-lookup"><span data-stu-id="a7e99-105">Method</span></span>|<span data-ttu-id="a7e99-106">描述</span><span class="sxs-lookup"><span data-stu-id="a7e99-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7e99-107">SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="a7e99-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="a7e99-108">通知主机运行时垃圾回收或其他挂起之后恢复线程。</span><span class="sxs-lookup"><span data-stu-id="a7e99-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="a7e99-109">SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="a7e99-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="a7e99-110">通知垃圾回收的线程挂起或其他挂起开始运行时主机。</span><span class="sxs-lookup"><span data-stu-id="a7e99-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="a7e99-111">ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="a7e99-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="a7e99-112">通知主机进行调用的线程即将进行阻止，可能的垃圾回收或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="a7e99-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7e99-113">要求</span><span class="sxs-lookup"><span data-stu-id="a7e99-113">Requirements</span></span>  
 <span data-ttu-id="a7e99-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e99-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7e99-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7e99-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7e99-116">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a7e99-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a7e99-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a7e99-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7e99-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7e99-118">See also</span></span>

- [<span data-ttu-id="a7e99-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="a7e99-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
