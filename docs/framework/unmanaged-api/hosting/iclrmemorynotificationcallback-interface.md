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
ms.openlocfilehash: 52fc21044d345998ad72c045cdf5e80a8a03a38e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703798"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="0b93c-102">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="0b93c-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="0b93c-103">允许主机使用类似于 Win32 函数的方法来报告内存压力情况 `CreateMemoryResourceNotification` 。</span><span class="sxs-lookup"><span data-stu-id="0b93c-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b93c-104">方法</span><span class="sxs-lookup"><span data-stu-id="0b93c-104">Methods</span></span>  
  
|<span data-ttu-id="0b93c-105">方法</span><span class="sxs-lookup"><span data-stu-id="0b93c-105">Method</span></span>|<span data-ttu-id="0b93c-106">说明</span><span class="sxs-lookup"><span data-stu-id="0b93c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b93c-107">OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="0b93c-107">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="0b93c-108">向公共语言运行时（CLR）通知计算机上的内存负载。</span><span class="sxs-lookup"><span data-stu-id="0b93c-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b93c-109">备注</span><span class="sxs-lookup"><span data-stu-id="0b93c-109">Remarks</span></span>  
 <span data-ttu-id="0b93c-110">主机使用 `ICLRMemoryNotificationCallback` 接口请求 CLR 释放内存资源。</span><span class="sxs-lookup"><span data-stu-id="0b93c-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b93c-111">要求</span><span class="sxs-lookup"><span data-stu-id="0b93c-111">Requirements</span></span>  
 <span data-ttu-id="0b93c-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b93c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b93c-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0b93c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b93c-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="0b93c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b93c-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b93c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b93c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b93c-116">See also</span></span>

- [<span data-ttu-id="0b93c-117">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="0b93c-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="0b93c-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="0b93c-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
