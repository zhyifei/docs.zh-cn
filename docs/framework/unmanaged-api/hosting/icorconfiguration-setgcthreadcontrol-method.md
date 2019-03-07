---
title: ICorConfiguration::SetGCThreadControl 方法
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97af133aa573e3b9c74f6bdbb4410f4d12214d67
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491396"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="4cf04-102">ICorConfiguration::SetGCThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="4cf04-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="4cf04-103">设置回调接口来调度线程，以防止因阻塞而垃圾回收的非运行时任务。</span><span class="sxs-lookup"><span data-stu-id="4cf04-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf04-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cf04-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cf04-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cf04-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="4cf04-106">[in]一个指向[IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)通知主机有关非运行时任务的线程的挂起的对象。</span><span class="sxs-lookup"><span data-stu-id="4cf04-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cf04-107">备注</span><span class="sxs-lookup"><span data-stu-id="4cf04-107">Remarks</span></span>  
 <span data-ttu-id="4cf04-108">主机可能选择内[igcthreadcontrol:: Threadisblockingforsuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)回调是否要重新计划一个线程。</span><span class="sxs-lookup"><span data-stu-id="4cf04-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cf04-109">要求</span><span class="sxs-lookup"><span data-stu-id="4cf04-109">Requirements</span></span>  
 <span data-ttu-id="4cf04-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cf04-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cf04-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4cf04-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cf04-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4cf04-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cf04-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cf04-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf04-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cf04-114">See also</span></span>
- [<span data-ttu-id="4cf04-115">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="4cf04-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
