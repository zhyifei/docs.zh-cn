---
title: "IGCHost::SetVirtualMemLimit 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.SetVirtualMemLimit
api_location: mscoree.dll
api_type: COM
f1_keywords: SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ff3b5a8ba559530561503a3678a37ac0b9480907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="4c6be-102">IGCHost::SetVirtualMemLimit 方法</span><span class="sxs-lookup"><span data-stu-id="4c6be-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="4c6be-103">设置运行时的虚拟内存的最大大小。</span><span class="sxs-lookup"><span data-stu-id="4c6be-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c6be-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c6be-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c6be-105">参数</span><span class="sxs-lookup"><span data-stu-id="4c6be-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="4c6be-106">[in]最大的大小，以兆字节为单位，运行时的虚拟内存。</span><span class="sxs-lookup"><span data-stu-id="4c6be-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c6be-107">备注</span><span class="sxs-lookup"><span data-stu-id="4c6be-107">Remarks</span></span>  
 <span data-ttu-id="4c6be-108">可以动态更改运行时的虚拟内存的最大大小。</span><span class="sxs-lookup"><span data-stu-id="4c6be-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c6be-109">要求</span><span class="sxs-lookup"><span data-stu-id="4c6be-109">Requirements</span></span>  
 <span data-ttu-id="4c6be-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c6be-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c6be-111">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="4c6be-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="4c6be-112">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4c6be-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c6be-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c6be-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6be-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c6be-114">See Also</span></span>  
 [<span data-ttu-id="4c6be-115">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="4c6be-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
