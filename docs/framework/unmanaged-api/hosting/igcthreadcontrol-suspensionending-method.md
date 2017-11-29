---
title: "IGCThreadControl::SuspensionEnding 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4460d2b0eaf10d20ddd0c3641279a8ffc05c245
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="3a15e-102">IGCThreadControl::SuspensionEnding 方法</span><span class="sxs-lookup"><span data-stu-id="3a15e-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="3a15e-103">通知主机运行时正在恢复后垃圾回收或其他挂起的线程。</span><span class="sxs-lookup"><span data-stu-id="3a15e-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a15e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a15e-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a15e-105">参数</span><span class="sxs-lookup"><span data-stu-id="3a15e-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="3a15e-106">[in]对其执行垃圾回收生成。</span><span class="sxs-lookup"><span data-stu-id="3a15e-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a15e-107">备注</span><span class="sxs-lookup"><span data-stu-id="3a15e-107">Remarks</span></span>  
 <span data-ttu-id="3a15e-108">不重新计划在任何线程`SuspensionEnding`回调。</span><span class="sxs-lookup"><span data-stu-id="3a15e-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a15e-109">要求</span><span class="sxs-lookup"><span data-stu-id="3a15e-109">Requirements</span></span>  
 <span data-ttu-id="3a15e-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3a15e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a15e-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3a15e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a15e-112">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3a15e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a15e-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a15e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a15e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a15e-114">See Also</span></span>  
 [<span data-ttu-id="3a15e-115">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="3a15e-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
