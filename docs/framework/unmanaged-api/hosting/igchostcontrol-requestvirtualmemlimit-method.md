---
title: IGCHostControl::RequestVirtualMemLimit 方法
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
ms.openlocfilehash: d4814e44b1a5311cf6800c804df7a7e11000cbab
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805140"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="8f92f-102">IGCHostControl::RequestVirtualMemLimit 方法</span><span class="sxs-lookup"><span data-stu-id="8f92f-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="8f92f-103">请求主机更改虚拟内存的限制。</span><span class="sxs-lookup"><span data-stu-id="8f92f-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f92f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f92f-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f92f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8f92f-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="8f92f-106">中要分配的请求的内存大小。</span><span class="sxs-lookup"><span data-stu-id="8f92f-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="8f92f-107">[in，out]一个指针，指向所分配的内存的实际大小。</span><span class="sxs-lookup"><span data-stu-id="8f92f-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f92f-108">要求</span><span class="sxs-lookup"><span data-stu-id="8f92f-108">Requirements</span></span>  
 <span data-ttu-id="8f92f-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f92f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f92f-110">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8f92f-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f92f-111">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8f92f-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f92f-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f92f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f92f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f92f-113">See also</span></span>

- [<span data-ttu-id="8f92f-114">IGCHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="8f92f-114">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)
