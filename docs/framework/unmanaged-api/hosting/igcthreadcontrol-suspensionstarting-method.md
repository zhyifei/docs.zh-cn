---
title: "IGCThreadControl::SuspensionStarting 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9d5f403c2880d0079a89c6de5c2ad9aa4f8d9fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="508a2-102">IGCThreadControl::SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="508a2-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="508a2-103">通知主机运行时正在开始垃圾回收的线程挂起或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="508a2-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="508a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="508a2-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="508a2-105">备注</span><span class="sxs-lookup"><span data-stu-id="508a2-105">Remarks</span></span>  
 <span data-ttu-id="508a2-106">不重新计划在任何线程`SuspensionStarting`回调。</span><span class="sxs-lookup"><span data-stu-id="508a2-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="508a2-107">要求</span><span class="sxs-lookup"><span data-stu-id="508a2-107">Requirements</span></span>  
 <span data-ttu-id="508a2-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="508a2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="508a2-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="508a2-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="508a2-110">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="508a2-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="508a2-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="508a2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="508a2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="508a2-112">See Also</span></span>  
 [<span data-ttu-id="508a2-113">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="508a2-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
