---
title: IGCThreadControl::ThreadIsBlockingForSuspension 方法
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8609b32ad2dea699b5b248b2b8bb3d81ec744043
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779475"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="1760b-102">IGCThreadControl::ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="1760b-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="1760b-103">通知主机进行调用的线程即将进行阻止，可能的垃圾回收或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="1760b-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1760b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1760b-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="1760b-105">备注</span><span class="sxs-lookup"><span data-stu-id="1760b-105">Remarks</span></span>  
 <span data-ttu-id="1760b-106">主机可以选择在`ThreadIsBlockingForSuspension`回调是否要重新计划一个线程。</span><span class="sxs-lookup"><span data-stu-id="1760b-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1760b-107">要求</span><span class="sxs-lookup"><span data-stu-id="1760b-107">Requirements</span></span>  
 <span data-ttu-id="1760b-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1760b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1760b-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1760b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1760b-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1760b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1760b-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1760b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1760b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1760b-112">See also</span></span>

- [<span data-ttu-id="1760b-113">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="1760b-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
