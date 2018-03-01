---
title: "IDebuggerThreadControl 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 297a66f9466b00dec4d32f7d8a6e2bd13b6e5655
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="3e7c3-102">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="3e7c3-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="3e7c3-103">提供用于通知主机有关阻止和取消阻止的线程调试服务的方法。</span><span class="sxs-lookup"><span data-stu-id="3e7c3-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e7c3-104">方法</span><span class="sxs-lookup"><span data-stu-id="3e7c3-104">Methods</span></span>  
  
|<span data-ttu-id="3e7c3-105">方法</span><span class="sxs-lookup"><span data-stu-id="3e7c3-105">Method</span></span>|<span data-ttu-id="3e7c3-106">描述</span><span class="sxs-lookup"><span data-stu-id="3e7c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e7c3-107">ThreadIsBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="3e7c3-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="3e7c3-108">通知正在发送此回调的线程即将主机到调试服务内的块。</span><span class="sxs-lookup"><span data-stu-id="3e7c3-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="3e7c3-109">ReleaseAllRuntimeThreads 方法</span><span class="sxs-lookup"><span data-stu-id="3e7c3-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="3e7c3-110">通知主机调试服务即将释放所有受阻的线程。</span><span class="sxs-lookup"><span data-stu-id="3e7c3-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="3e7c3-111">StartBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="3e7c3-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="3e7c3-112">通知主机调试服务即将开始阻止所有线程。</span><span class="sxs-lookup"><span data-stu-id="3e7c3-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e7c3-113">惠?</span><span class="sxs-lookup"><span data-stu-id="3e7c3-113">Requirements</span></span>  
 <span data-ttu-id="3e7c3-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e7c3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e7c3-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e7c3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e7c3-116">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3e7c3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e7c3-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e7c3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e7c3-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e7c3-118">See Also</span></span>  
 [<span data-ttu-id="3e7c3-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="3e7c3-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
