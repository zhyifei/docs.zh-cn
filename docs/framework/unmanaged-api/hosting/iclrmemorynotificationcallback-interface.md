---
title: ICLRMemoryNotificationCallback 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: e980356ad592e137df7d08dadd77431b0e295380
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141000"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="ba270-102">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ba270-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="ba270-103">允许主机使用类似于 Win32 `CreateMemoryResourceNotification` 函数的方法来报告内存压力情况。</span><span class="sxs-lookup"><span data-stu-id="ba270-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba270-104">方法</span><span class="sxs-lookup"><span data-stu-id="ba270-104">Methods</span></span>  
  
|<span data-ttu-id="ba270-105">方法</span><span class="sxs-lookup"><span data-stu-id="ba270-105">Method</span></span>|<span data-ttu-id="ba270-106">描述</span><span class="sxs-lookup"><span data-stu-id="ba270-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba270-107">OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="ba270-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="ba270-108">向公共语言运行时（CLR）通知计算机上的内存负载。</span><span class="sxs-lookup"><span data-stu-id="ba270-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba270-109">备注</span><span class="sxs-lookup"><span data-stu-id="ba270-109">Remarks</span></span>  
 <span data-ttu-id="ba270-110">主机使用 `ICLRMemoryNotificationCallback` 接口来请求 CLR 释放内存资源。</span><span class="sxs-lookup"><span data-stu-id="ba270-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba270-111">要求</span><span class="sxs-lookup"><span data-stu-id="ba270-111">Requirements</span></span>  
 <span data-ttu-id="ba270-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba270-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba270-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ba270-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba270-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ba270-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba270-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba270-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba270-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba270-116">See also</span></span>

- [<span data-ttu-id="ba270-117">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="ba270-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="ba270-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="ba270-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
