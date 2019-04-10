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
ms.openlocfilehash: 948b18832ccfc5e0fc2e42ee58e6444a581de260
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209680"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="dd154-102">IGCHostControl::RequestVirtualMemLimit 方法</span><span class="sxs-lookup"><span data-stu-id="dd154-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="dd154-103">请求主机后，若要更改虚拟内存的限制。</span><span class="sxs-lookup"><span data-stu-id="dd154-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd154-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd154-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd154-105">参数</span><span class="sxs-lookup"><span data-stu-id="dd154-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="dd154-106">[in]要分配的内存请求的大小。</span><span class="sxs-lookup"><span data-stu-id="dd154-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="dd154-107">[in、 out]指向分配的内存的实际大小的指针。</span><span class="sxs-lookup"><span data-stu-id="dd154-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd154-108">要求</span><span class="sxs-lookup"><span data-stu-id="dd154-108">Requirements</span></span>  
 <span data-ttu-id="dd154-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd154-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd154-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd154-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd154-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dd154-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="dd154-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="dd154-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd154-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd154-113">See also</span></span>

- [<span data-ttu-id="dd154-114">IGCHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="dd154-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
