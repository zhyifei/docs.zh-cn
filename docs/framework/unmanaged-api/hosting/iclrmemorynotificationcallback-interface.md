---
title: "ICLRMemoryNotificationCallback 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc09e3668dc814360de0256c2476ffa7b61462ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="586b5-102">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="586b5-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="586b5-103">允许使用类似于 Win32 方法报告内存压力情况主机`CreateMemoryResourceNotification`函数。</span><span class="sxs-lookup"><span data-stu-id="586b5-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="586b5-104">方法</span><span class="sxs-lookup"><span data-stu-id="586b5-104">Methods</span></span>  
  
|<span data-ttu-id="586b5-105">方法</span><span class="sxs-lookup"><span data-stu-id="586b5-105">Method</span></span>|<span data-ttu-id="586b5-106">描述</span><span class="sxs-lookup"><span data-stu-id="586b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="586b5-107">OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="586b5-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="586b5-108">通知在计算机上的内存负载公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="586b5-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="586b5-109">备注</span><span class="sxs-lookup"><span data-stu-id="586b5-109">Remarks</span></span>  
 <span data-ttu-id="586b5-110">主机使用`ICLRMemoryNotificationCallback`接口来请求 CLR 释放内存资源。</span><span class="sxs-lookup"><span data-stu-id="586b5-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="586b5-111">惠?</span><span class="sxs-lookup"><span data-stu-id="586b5-111">Requirements</span></span>  
 <span data-ttu-id="586b5-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="586b5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="586b5-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="586b5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="586b5-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="586b5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="586b5-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="586b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="586b5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="586b5-116">See Also</span></span>  
 [<span data-ttu-id="586b5-117">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="586b5-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="586b5-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="586b5-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
