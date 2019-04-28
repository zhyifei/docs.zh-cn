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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699651"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="221de-102">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="221de-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="221de-103">提供用于通知主机有关阻止和取消阻止的线程的调试服务的方法。</span><span class="sxs-lookup"><span data-stu-id="221de-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="221de-104">方法</span><span class="sxs-lookup"><span data-stu-id="221de-104">Methods</span></span>  
  
|<span data-ttu-id="221de-105">方法</span><span class="sxs-lookup"><span data-stu-id="221de-105">Method</span></span>|<span data-ttu-id="221de-106">描述</span><span class="sxs-lookup"><span data-stu-id="221de-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="221de-107">ThreadIsBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="221de-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="221de-108">通知主机有关的发送此回调的线程到块中的调试服务。</span><span class="sxs-lookup"><span data-stu-id="221de-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="221de-109">ReleaseAllRuntimeThreads 方法</span><span class="sxs-lookup"><span data-stu-id="221de-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="221de-110">通知主机调试服务即将发布所有被阻止的线程。</span><span class="sxs-lookup"><span data-stu-id="221de-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="221de-111">StartBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="221de-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="221de-112">通知主机调试服务即将启动阻塞所有线程。</span><span class="sxs-lookup"><span data-stu-id="221de-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="221de-113">要求</span><span class="sxs-lookup"><span data-stu-id="221de-113">Requirements</span></span>  
 <span data-ttu-id="221de-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="221de-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="221de-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="221de-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="221de-116">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="221de-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="221de-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="221de-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221de-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="221de-118">See also</span></span>

- [<span data-ttu-id="221de-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="221de-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
