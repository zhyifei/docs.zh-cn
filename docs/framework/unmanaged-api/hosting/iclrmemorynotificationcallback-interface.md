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
ms.openlocfilehash: c98ece9d60571034f3298f15897b10c4d8fb06f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948542"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="77bf4-102">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="77bf4-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="77bf4-103">允许使用类似于 Win32 方法报告内存压力情况主机`CreateMemoryResourceNotification`函数。</span><span class="sxs-lookup"><span data-stu-id="77bf4-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77bf4-104">方法</span><span class="sxs-lookup"><span data-stu-id="77bf4-104">Methods</span></span>  
  
|<span data-ttu-id="77bf4-105">方法</span><span class="sxs-lookup"><span data-stu-id="77bf4-105">Method</span></span>|<span data-ttu-id="77bf4-106">描述</span><span class="sxs-lookup"><span data-stu-id="77bf4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77bf4-107">OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="77bf4-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="77bf4-108">通知公共语言运行时 (CLR) 的计算机上的内存负载。</span><span class="sxs-lookup"><span data-stu-id="77bf4-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77bf4-109">备注</span><span class="sxs-lookup"><span data-stu-id="77bf4-109">Remarks</span></span>  
 <span data-ttu-id="77bf4-110">主机使用`ICLRMemoryNotificationCallback`接口请求 CLR 释放内存资源。</span><span class="sxs-lookup"><span data-stu-id="77bf4-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77bf4-111">要求</span><span class="sxs-lookup"><span data-stu-id="77bf4-111">Requirements</span></span>  
 <span data-ttu-id="77bf4-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77bf4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77bf4-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77bf4-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77bf4-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="77bf4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77bf4-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77bf4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77bf4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="77bf4-116">See also</span></span>

- [<span data-ttu-id="77bf4-117">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="77bf4-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="77bf4-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="77bf4-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
