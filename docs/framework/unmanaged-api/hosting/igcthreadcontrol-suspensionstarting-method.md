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
ms.openlocfilehash: 1e1d63ab28276f69e5b3a762520db8f8300d05bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134761"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="69d03-102">IGCThreadControl::SuspensionStarting 方法</span><span class="sxs-lookup"><span data-stu-id="69d03-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="69d03-103">通知宿主运行时正在为垃圾回收或其他挂起开始线程挂起。</span><span class="sxs-lookup"><span data-stu-id="69d03-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69d03-104">语法</span><span class="sxs-lookup"><span data-stu-id="69d03-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="69d03-105">备注</span><span class="sxs-lookup"><span data-stu-id="69d03-105">Remarks</span></span>  
 <span data-ttu-id="69d03-106">请勿在 `SuspensionStarting` 回调期间重新计划任何线程。</span><span class="sxs-lookup"><span data-stu-id="69d03-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69d03-107">要求</span><span class="sxs-lookup"><span data-stu-id="69d03-107">Requirements</span></span>  
 <span data-ttu-id="69d03-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="69d03-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69d03-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="69d03-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69d03-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="69d03-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69d03-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69d03-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d03-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="69d03-112">See also</span></span>

- [<span data-ttu-id="69d03-113">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="69d03-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
