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
ms.openlocfilehash: 7613bc744ad4c2e172fc4f6dd7bf282fb3d9072c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179746"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="d8f64-102">IGCThreadControl::SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="d8f64-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="d8f64-103">通知垃圾回收的线程挂起或其他挂起开始运行时主机。</span><span class="sxs-lookup"><span data-stu-id="d8f64-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f64-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8f64-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="d8f64-105">备注</span><span class="sxs-lookup"><span data-stu-id="d8f64-105">Remarks</span></span>  
 <span data-ttu-id="d8f64-106">不重新计划在任何线程`SuspensionStarting`回调。</span><span class="sxs-lookup"><span data-stu-id="d8f64-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8f64-107">要求</span><span class="sxs-lookup"><span data-stu-id="d8f64-107">Requirements</span></span>  
 <span data-ttu-id="d8f64-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8f64-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8f64-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8f64-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8f64-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d8f64-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d8f64-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d8f64-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8f64-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8f64-112">See also</span></span>

- [<span data-ttu-id="d8f64-113">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="d8f64-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
