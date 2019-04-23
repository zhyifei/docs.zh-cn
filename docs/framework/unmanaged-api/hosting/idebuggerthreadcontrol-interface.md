---
title: IDebuggerThreadControl 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a551d3cc6ab3dd3887f232018f8201de4036d1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096831"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="426d5-102">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="426d5-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="426d5-103">提供用于通知主机有关阻止和取消阻止的线程的调试服务的方法。</span><span class="sxs-lookup"><span data-stu-id="426d5-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="426d5-104">方法</span><span class="sxs-lookup"><span data-stu-id="426d5-104">Methods</span></span>  
  
|<span data-ttu-id="426d5-105">方法</span><span class="sxs-lookup"><span data-stu-id="426d5-105">Method</span></span>|<span data-ttu-id="426d5-106">描述</span><span class="sxs-lookup"><span data-stu-id="426d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="426d5-107">ThreadIsBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="426d5-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="426d5-108">通知主机有关的发送此回调的线程到块中的调试服务。</span><span class="sxs-lookup"><span data-stu-id="426d5-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="426d5-109">ReleaseAllRuntimeThreads 方法</span><span class="sxs-lookup"><span data-stu-id="426d5-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="426d5-110">通知主机调试服务即将发布所有被阻止的线程。</span><span class="sxs-lookup"><span data-stu-id="426d5-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="426d5-111">StartBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="426d5-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="426d5-112">通知主机调试服务即将启动阻塞所有线程。</span><span class="sxs-lookup"><span data-stu-id="426d5-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="426d5-113">要求</span><span class="sxs-lookup"><span data-stu-id="426d5-113">Requirements</span></span>  
 <span data-ttu-id="426d5-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="426d5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="426d5-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="426d5-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="426d5-116">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="426d5-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="426d5-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="426d5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="426d5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="426d5-118">See also</span></span>

- [<span data-ttu-id="426d5-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="426d5-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
