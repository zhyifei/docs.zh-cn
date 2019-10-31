---
title: IDebuggerThreadControl::ReleaseAllRuntimeThreads 方法
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
ms.openlocfilehash: 9ae1aa6590366468166916e6a92d0b356eb37c27
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133145"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="21408-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads 方法</span><span class="sxs-lookup"><span data-stu-id="21408-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="21408-103">向宿主通知调试服务将要释放被阻止的所有线程。</span><span class="sxs-lookup"><span data-stu-id="21408-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21408-104">语法</span><span class="sxs-lookup"><span data-stu-id="21408-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="21408-105">备注</span><span class="sxs-lookup"><span data-stu-id="21408-105">Remarks</span></span>  
 <span data-ttu-id="21408-106">永远不会在运行时线程上调用 `ReleaseAllRuntimeThreads` 方法。</span><span class="sxs-lookup"><span data-stu-id="21408-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="21408-107">如果主机已阻止运行时线程，则它现在应释放它。</span><span class="sxs-lookup"><span data-stu-id="21408-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21408-108">要求</span><span class="sxs-lookup"><span data-stu-id="21408-108">Requirements</span></span>  
 <span data-ttu-id="21408-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21408-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21408-110">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="21408-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21408-111">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="21408-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21408-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21408-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21408-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="21408-113">See also</span></span>

- [<span data-ttu-id="21408-114">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="21408-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
