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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9324e1596913fdafb13239dbefd631cbe3c6ffe4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780493"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="1e3b5-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="1e3b5-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="1e3b5-103">通知主机有关的发送此回调的线程到块中的调试服务。</span><span class="sxs-lookup"><span data-stu-id="1e3b5-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e3b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e3b5-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="1e3b5-105">备注</span><span class="sxs-lookup"><span data-stu-id="1e3b5-105">Remarks</span></span>  
 <span data-ttu-id="1e3b5-106">`ThreadIsBlockingForDebugger`将始终在运行时线程上调用方法。</span><span class="sxs-lookup"><span data-stu-id="1e3b5-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="1e3b5-107">`ThreadIsBlockingForDebugger`方法使主机能够执行其他操作，而此线程受到阻止。</span><span class="sxs-lookup"><span data-stu-id="1e3b5-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e3b5-108">要求</span><span class="sxs-lookup"><span data-stu-id="1e3b5-108">Requirements</span></span>  
 <span data-ttu-id="1e3b5-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e3b5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e3b5-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e3b5-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e3b5-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1e3b5-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e3b5-112">**NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e3b5-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e3b5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e3b5-113">See also</span></span>

- [<span data-ttu-id="1e3b5-114">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="1e3b5-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
