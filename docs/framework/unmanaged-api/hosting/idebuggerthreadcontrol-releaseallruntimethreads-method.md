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
ms.openlocfilehash: 136dab5c05c310d85a5e18bcdc6da0de901d3ace
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227465"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="9cdd0-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads 方法</span><span class="sxs-lookup"><span data-stu-id="9cdd0-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="9cdd0-103">通知主机调试服务即将发布所有被阻止的线程。</span><span class="sxs-lookup"><span data-stu-id="9cdd0-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cdd0-104">语法</span><span class="sxs-lookup"><span data-stu-id="9cdd0-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="9cdd0-105">备注</span><span class="sxs-lookup"><span data-stu-id="9cdd0-105">Remarks</span></span>  
 <span data-ttu-id="9cdd0-106">`ReleaseAllRuntimeThreads`将永远不会在运行时线程上调用方法。</span><span class="sxs-lookup"><span data-stu-id="9cdd0-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="9cdd0-107">如果主机运行时线程被阻止，现在应将其释放。</span><span class="sxs-lookup"><span data-stu-id="9cdd0-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cdd0-108">要求</span><span class="sxs-lookup"><span data-stu-id="9cdd0-108">Requirements</span></span>  
 <span data-ttu-id="9cdd0-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9cdd0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cdd0-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9cdd0-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9cdd0-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9cdd0-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cdd0-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cdd0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cdd0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cdd0-113">See also</span></span>

- [<span data-ttu-id="9cdd0-114">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="9cdd0-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
