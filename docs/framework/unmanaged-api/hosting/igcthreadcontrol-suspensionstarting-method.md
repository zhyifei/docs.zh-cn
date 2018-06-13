---
title: IGCThreadControl::SuspensionStarting 方法
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95cbda3729c02b95557f9f700f1ea7c68aa450a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438010"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="100ee-102">IGCThreadControl::SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="100ee-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="100ee-103">通知主机运行时正在开始垃圾回收的线程挂起或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="100ee-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="100ee-104">语法</span><span class="sxs-lookup"><span data-stu-id="100ee-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="100ee-105">备注</span><span class="sxs-lookup"><span data-stu-id="100ee-105">Remarks</span></span>  
 <span data-ttu-id="100ee-106">不重新计划在任何线程`SuspensionStarting`回调。</span><span class="sxs-lookup"><span data-stu-id="100ee-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="100ee-107">要求</span><span class="sxs-lookup"><span data-stu-id="100ee-107">Requirements</span></span>  
 <span data-ttu-id="100ee-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="100ee-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="100ee-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="100ee-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="100ee-110">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="100ee-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="100ee-111">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="100ee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="100ee-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="100ee-112">See Also</span></span>  
 [<span data-ttu-id="100ee-113">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="100ee-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
