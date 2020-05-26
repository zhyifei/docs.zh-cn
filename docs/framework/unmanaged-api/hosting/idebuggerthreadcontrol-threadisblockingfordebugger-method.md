---
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger 方法
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
ms.openlocfilehash: f7cdc3fe9d52db56d0280bc602d3a9f2f54e8246
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805255"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="297fd-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="297fd-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="297fd-103">向宿主通知发送此回调的线程即将在调试服务中阻止。</span><span class="sxs-lookup"><span data-stu-id="297fd-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="297fd-104">语法</span><span class="sxs-lookup"><span data-stu-id="297fd-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="297fd-105">备注</span><span class="sxs-lookup"><span data-stu-id="297fd-105">Remarks</span></span>  
 <span data-ttu-id="297fd-106">在 `ThreadIsBlockingForDebugger` 运行时线程上将始终调用方法。</span><span class="sxs-lookup"><span data-stu-id="297fd-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="297fd-107">`ThreadIsBlockingForDebugger`方法使宿主有机会在线程阻塞时执行另一个操作。</span><span class="sxs-lookup"><span data-stu-id="297fd-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="297fd-108">要求</span><span class="sxs-lookup"><span data-stu-id="297fd-108">Requirements</span></span>  
 <span data-ttu-id="297fd-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="297fd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="297fd-110">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="297fd-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="297fd-111">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="297fd-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="297fd-112">**NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="297fd-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="297fd-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="297fd-113">See also</span></span>

- [<span data-ttu-id="297fd-114">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="297fd-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
