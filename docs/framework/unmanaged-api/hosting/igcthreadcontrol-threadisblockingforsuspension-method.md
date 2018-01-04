---
title: "IGCThreadControl::ThreadIsBlockingForSuspension 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.ThreadIsBlockingForSuspension
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cb7cfbab18334f1892c24225311160179920f81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="40b47-102">IGCThreadControl::ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="40b47-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="40b47-103">通知主机进行调用的线程即将进行阻止，可能针对垃圾回收或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="40b47-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b47-104">语法</span><span class="sxs-lookup"><span data-stu-id="40b47-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="40b47-105">备注</span><span class="sxs-lookup"><span data-stu-id="40b47-105">Remarks</span></span>  
 <span data-ttu-id="40b47-106">主机可以选择在`ThreadIsBlockingForSuspension`回调是否要重新计划线程。</span><span class="sxs-lookup"><span data-stu-id="40b47-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40b47-107">惠?</span><span class="sxs-lookup"><span data-stu-id="40b47-107">Requirements</span></span>  
 <span data-ttu-id="40b47-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40b47-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40b47-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="40b47-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40b47-110">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="40b47-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40b47-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40b47-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b47-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="40b47-112">See Also</span></span>  
 [<span data-ttu-id="40b47-113">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="40b47-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
