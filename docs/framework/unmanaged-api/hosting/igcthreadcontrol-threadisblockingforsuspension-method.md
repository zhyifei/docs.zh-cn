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
ms.openlocfilehash: e6534c3085b70b590c2dcc3f50cf0253bd5e6682
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134754"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="a2ae1-102">IGCThreadControl::ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="a2ae1-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="a2ae1-103">通知宿主正在进行调用的线程将要阻止，可能用于垃圾回收或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="a2ae1-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ae1-104">语法</span><span class="sxs-lookup"><span data-stu-id="a2ae1-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="a2ae1-105">备注</span><span class="sxs-lookup"><span data-stu-id="a2ae1-105">Remarks</span></span>  
 <span data-ttu-id="a2ae1-106">宿主可以在 `ThreadIsBlockingForSuspension` 回调中选择是否重新计划线程。</span><span class="sxs-lookup"><span data-stu-id="a2ae1-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2ae1-107">要求</span><span class="sxs-lookup"><span data-stu-id="a2ae1-107">Requirements</span></span>  
 <span data-ttu-id="a2ae1-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ae1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2ae1-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a2ae1-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2ae1-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a2ae1-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2ae1-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2ae1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ae1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2ae1-112">See also</span></span>

- [<span data-ttu-id="a2ae1-113">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="a2ae1-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
