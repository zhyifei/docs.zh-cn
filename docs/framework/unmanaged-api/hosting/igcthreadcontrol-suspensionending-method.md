---
title: IGCThreadControl::SuspensionEnding 方法
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffee1550c64f1ce7c438580ce78a497aeeb99f3a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468762"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="82455-102">IGCThreadControl::SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="82455-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="82455-103">通知主机运行时垃圾回收或其他挂起之后恢复线程。</span><span class="sxs-lookup"><span data-stu-id="82455-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82455-104">语法</span><span class="sxs-lookup"><span data-stu-id="82455-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82455-105">参数</span><span class="sxs-lookup"><span data-stu-id="82455-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="82455-106">[in]对其执行垃圾回收生成。</span><span class="sxs-lookup"><span data-stu-id="82455-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82455-107">备注</span><span class="sxs-lookup"><span data-stu-id="82455-107">Remarks</span></span>  
 <span data-ttu-id="82455-108">不重新计划在任何线程`SuspensionEnding`回调。</span><span class="sxs-lookup"><span data-stu-id="82455-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82455-109">要求</span><span class="sxs-lookup"><span data-stu-id="82455-109">Requirements</span></span>  
 <span data-ttu-id="82455-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82455-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82455-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82455-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82455-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="82455-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82455-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82455-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82455-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="82455-114">See also</span></span>
- [<span data-ttu-id="82455-115">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="82455-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
