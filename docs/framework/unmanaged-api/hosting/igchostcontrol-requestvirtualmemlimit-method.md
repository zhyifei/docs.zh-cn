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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbb0b6191c74c2b7ebdc8267701f246c17b016f9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779528"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="1d05d-102">IGCHostControl::RequestVirtualMemLimit 方法</span><span class="sxs-lookup"><span data-stu-id="1d05d-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="1d05d-103">请求主机后，若要更改虚拟内存的限制。</span><span class="sxs-lookup"><span data-stu-id="1d05d-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d05d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d05d-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d05d-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d05d-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="1d05d-106">[in]要分配的内存请求的大小。</span><span class="sxs-lookup"><span data-stu-id="1d05d-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="1d05d-107">[in、 out]指向分配的内存的实际大小的指针。</span><span class="sxs-lookup"><span data-stu-id="1d05d-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d05d-108">要求</span><span class="sxs-lookup"><span data-stu-id="1d05d-108">Requirements</span></span>  
 <span data-ttu-id="1d05d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d05d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d05d-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d05d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d05d-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1d05d-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d05d-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d05d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d05d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d05d-113">See also</span></span>

- [<span data-ttu-id="1d05d-114">IGCHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="1d05d-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
