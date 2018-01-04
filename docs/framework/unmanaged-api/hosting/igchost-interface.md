---
title: "IGCHost 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost
helpviewer_keywords: IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77a2cab35785aa39571d39bdd369fa26cdbcd1d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="igchost-interface"></a><span data-ttu-id="cc0d1-102">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="cc0d1-102">IGCHost Interface</span></span>
<span data-ttu-id="cc0d1-103">提供用于获取有关垃圾回收系统的信息以及控制垃圾回收的某些方面的方法。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc0d1-104">从开始[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，你可以使用[igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法设置为值的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小大于`DWORD`施加的限制， [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc0d1-105">此接口是仅供专家使用。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-105">This interface is for expert usage only.</span></span> <span data-ttu-id="cc0d1-106">如果使用不当，它可能会影响应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc0d1-107">方法</span><span class="sxs-lookup"><span data-stu-id="cc0d1-107">Methods</span></span>  
  
|<span data-ttu-id="cc0d1-108">方法</span><span class="sxs-lookup"><span data-stu-id="cc0d1-108">Method</span></span>|<span data-ttu-id="cc0d1-109">描述</span><span class="sxs-lookup"><span data-stu-id="cc0d1-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc0d1-110">Collect 方法</span><span class="sxs-lookup"><span data-stu-id="cc0d1-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="cc0d1-111">强制回收进行回收对给定的代，而无论当前的垃圾回收的状态。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="cc0d1-112">GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="cc0d1-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="cc0d1-113">获取垃圾回收系统的当前状态的统计信息。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="cc0d1-114">GetThreadStats 方法</span><span class="sxs-lookup"><span data-stu-id="cc0d1-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="cc0d1-115">获取垃圾回收的每个线程统计信息。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="cc0d1-116">SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="cc0d1-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="cc0d1-117">为第 0 代中设置的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="cc0d1-118">SetVirtualMemLimit 方法</span><span class="sxs-lookup"><span data-stu-id="cc0d1-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="cc0d1-119">设置运行时的虚拟内存的最大大小。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc0d1-120">惠?</span><span class="sxs-lookup"><span data-stu-id="cc0d1-120">Requirements</span></span>  
 <span data-ttu-id="cc0d1-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc0d1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc0d1-122">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="cc0d1-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="cc0d1-123">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cc0d1-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc0d1-124">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc0d1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0d1-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc0d1-125">See Also</span></span>  
 [<span data-ttu-id="cc0d1-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="cc0d1-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="cc0d1-127">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="cc0d1-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
