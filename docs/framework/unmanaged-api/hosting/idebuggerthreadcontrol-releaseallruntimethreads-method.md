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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09895294c4678cdb1dd033076cfb42853aa06b2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780502"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="24848-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads 方法</span><span class="sxs-lookup"><span data-stu-id="24848-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="24848-103">通知主机调试服务即将发布所有被阻止的线程。</span><span class="sxs-lookup"><span data-stu-id="24848-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24848-104">语法</span><span class="sxs-lookup"><span data-stu-id="24848-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="24848-105">备注</span><span class="sxs-lookup"><span data-stu-id="24848-105">Remarks</span></span>  
 <span data-ttu-id="24848-106">`ReleaseAllRuntimeThreads`将永远不会在运行时线程上调用方法。</span><span class="sxs-lookup"><span data-stu-id="24848-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="24848-107">如果主机运行时线程被阻止，现在应将其释放。</span><span class="sxs-lookup"><span data-stu-id="24848-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24848-108">要求</span><span class="sxs-lookup"><span data-stu-id="24848-108">Requirements</span></span>  
 <span data-ttu-id="24848-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24848-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24848-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="24848-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24848-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="24848-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24848-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24848-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24848-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="24848-113">See also</span></span>

- [<span data-ttu-id="24848-114">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="24848-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
