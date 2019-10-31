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
ms.openlocfilehash: f43ee6d9a3832fca1766ec27c9f02d1aab2f5b8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127763"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="e2117-102">ICorConfiguration::SetGCThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="e2117-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="e2117-103">设置回调接口，用于为非运行时任务计划线程，否则将阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="e2117-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2117-104">语法</span><span class="sxs-lookup"><span data-stu-id="e2117-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2117-105">参数</span><span class="sxs-lookup"><span data-stu-id="e2117-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="e2117-106">中指向[IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)对象的指针，该对象向宿主通知非运行时任务的线程挂起。</span><span class="sxs-lookup"><span data-stu-id="e2117-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2117-107">备注</span><span class="sxs-lookup"><span data-stu-id="e2117-107">Remarks</span></span>  
 <span data-ttu-id="e2117-108">宿主可以在[IGCThreadControl：： ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)回调中选择是否重新计划线程。</span><span class="sxs-lookup"><span data-stu-id="e2117-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2117-109">要求</span><span class="sxs-lookup"><span data-stu-id="e2117-109">Requirements</span></span>  
 <span data-ttu-id="e2117-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2117-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2117-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e2117-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2117-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e2117-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2117-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2117-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2117-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2117-114">See also</span></span>

- [<span data-ttu-id="e2117-115">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="e2117-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
