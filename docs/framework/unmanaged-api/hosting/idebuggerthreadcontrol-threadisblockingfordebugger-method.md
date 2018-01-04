---
title: "IDebuggerThreadControl::ThreadIsBlockingForDebugger 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59a4c13e84414dcd10b217134334777a745431c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="8ec21-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="8ec21-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="8ec21-103">通知正在发送此回调的线程即将主机到调试服务内的块。</span><span class="sxs-lookup"><span data-stu-id="8ec21-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec21-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ec21-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ec21-105">备注</span><span class="sxs-lookup"><span data-stu-id="8ec21-105">Remarks</span></span>  
 <span data-ttu-id="8ec21-106">`ThreadIsBlockingForDebugger`始终将在运行时线程上调用方法。</span><span class="sxs-lookup"><span data-stu-id="8ec21-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="8ec21-107">`ThreadIsBlockingForDebugger`方法，该主机能够执行其他操作，而此线程受到阻止。</span><span class="sxs-lookup"><span data-stu-id="8ec21-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ec21-108">惠?</span><span class="sxs-lookup"><span data-stu-id="8ec21-108">Requirements</span></span>  
 <span data-ttu-id="8ec21-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ec21-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ec21-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8ec21-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ec21-111">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8ec21-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ec21-112">**NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ec21-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec21-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ec21-113">See Also</span></span>  
 [<span data-ttu-id="8ec21-114">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="8ec21-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
