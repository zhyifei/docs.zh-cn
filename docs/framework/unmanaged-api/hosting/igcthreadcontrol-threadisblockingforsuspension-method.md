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
ms.openlocfilehash: b5f6d7d40274972438a01313bc6aaec475b8e0c6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805092"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="a322d-102">IGCThreadControl::ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="a322d-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="a322d-103">通知宿主正在进行调用的线程将要阻止，可能用于垃圾回收或其他挂起。</span><span class="sxs-lookup"><span data-stu-id="a322d-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a322d-104">语法</span><span class="sxs-lookup"><span data-stu-id="a322d-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="a322d-105">备注</span><span class="sxs-lookup"><span data-stu-id="a322d-105">Remarks</span></span>  
 <span data-ttu-id="a322d-106">宿主可以在回调内选择 `ThreadIsBlockingForSuspension` 是否重新计划线程。</span><span class="sxs-lookup"><span data-stu-id="a322d-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a322d-107">要求</span><span class="sxs-lookup"><span data-stu-id="a322d-107">Requirements</span></span>  
 <span data-ttu-id="a322d-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a322d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a322d-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a322d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a322d-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a322d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a322d-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a322d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a322d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a322d-112">See also</span></span>

- [<span data-ttu-id="a322d-113">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="a322d-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
