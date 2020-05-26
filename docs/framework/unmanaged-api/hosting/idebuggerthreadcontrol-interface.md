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
ms.openlocfilehash: 82c6113f4df3334500128df22f7e9ce8d4bf151f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805281"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="1f135-102">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="1f135-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="1f135-103">提供一些方法，用于通知宿主调试服务阻止和取消阻止线程。</span><span class="sxs-lookup"><span data-stu-id="1f135-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f135-104">方法</span><span class="sxs-lookup"><span data-stu-id="1f135-104">Methods</span></span>  
  
|<span data-ttu-id="1f135-105">方法</span><span class="sxs-lookup"><span data-stu-id="1f135-105">Method</span></span>|<span data-ttu-id="1f135-106">说明</span><span class="sxs-lookup"><span data-stu-id="1f135-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f135-107">ThreadIsBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="1f135-107">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="1f135-108">向宿主通知发送此回调的线程即将在调试服务中阻止。</span><span class="sxs-lookup"><span data-stu-id="1f135-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="1f135-109">ReleaseAllRuntimeThreads 方法</span><span class="sxs-lookup"><span data-stu-id="1f135-109">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="1f135-110">向宿主通知调试服务将要释放被阻止的所有线程。</span><span class="sxs-lookup"><span data-stu-id="1f135-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="1f135-111">StartBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="1f135-111">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="1f135-112">通知宿主调试服务即将开始阻塞所有线程。</span><span class="sxs-lookup"><span data-stu-id="1f135-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f135-113">要求</span><span class="sxs-lookup"><span data-stu-id="1f135-113">Requirements</span></span>  
 <span data-ttu-id="1f135-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f135-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f135-115">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1f135-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f135-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1f135-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f135-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f135-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f135-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f135-118">See also</span></span>

- [<span data-ttu-id="1f135-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="1f135-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
