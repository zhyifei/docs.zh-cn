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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3167d288a57575af85a9cb50f5c0cd82c8e9cc9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702790"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="288f2-102">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="288f2-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="288f2-103">允许使用类似于 Win32 方法报告内存压力情况主机`CreateMemoryResourceNotification`函数。</span><span class="sxs-lookup"><span data-stu-id="288f2-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="288f2-104">方法</span><span class="sxs-lookup"><span data-stu-id="288f2-104">Methods</span></span>  
  
|<span data-ttu-id="288f2-105">方法</span><span class="sxs-lookup"><span data-stu-id="288f2-105">Method</span></span>|<span data-ttu-id="288f2-106">描述</span><span class="sxs-lookup"><span data-stu-id="288f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="288f2-107">OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="288f2-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="288f2-108">通知公共语言运行时 (CLR) 的计算机上的内存负载。</span><span class="sxs-lookup"><span data-stu-id="288f2-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="288f2-109">备注</span><span class="sxs-lookup"><span data-stu-id="288f2-109">Remarks</span></span>  
 <span data-ttu-id="288f2-110">主机使用`ICLRMemoryNotificationCallback`接口请求 CLR 释放内存资源。</span><span class="sxs-lookup"><span data-stu-id="288f2-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="288f2-111">要求</span><span class="sxs-lookup"><span data-stu-id="288f2-111">Requirements</span></span>  
 <span data-ttu-id="288f2-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="288f2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="288f2-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="288f2-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="288f2-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="288f2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="288f2-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="288f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="288f2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="288f2-116">See also</span></span>
- [<span data-ttu-id="288f2-117">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="288f2-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="288f2-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="288f2-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
