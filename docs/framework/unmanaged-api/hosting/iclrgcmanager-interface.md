---
title: "ICLRGCManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager
helpviewer_keywords: ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6cc6c84d57e4114a28a8b363b99b98f3c4d21410
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="a85d7-102">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="a85d7-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="a85d7-103">提供允许的主机与公共语言运行时的垃圾回收系统进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="a85d7-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a85d7-104">从开始[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，你可以使用[iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法设置为值的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小更大比`DWORD`施加的限制， [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a85d7-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a85d7-105">方法</span><span class="sxs-lookup"><span data-stu-id="a85d7-105">Methods</span></span>  
  
|<span data-ttu-id="a85d7-106">方法</span><span class="sxs-lookup"><span data-stu-id="a85d7-106">Method</span></span>|<span data-ttu-id="a85d7-107">描述</span><span class="sxs-lookup"><span data-stu-id="a85d7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a85d7-108">Collect 方法</span><span class="sxs-lookup"><span data-stu-id="a85d7-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="a85d7-109">强制指定代的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="a85d7-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="a85d7-110">GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="a85d7-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="a85d7-111">获取一组有关垃圾回收系统的当前统计信息。</span><span class="sxs-lookup"><span data-stu-id="a85d7-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="a85d7-112">SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="a85d7-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="a85d7-113">设置的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小。</span><span class="sxs-lookup"><span data-stu-id="a85d7-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a85d7-114">备注</span><span class="sxs-lookup"><span data-stu-id="a85d7-114">Remarks</span></span>  
 <span data-ttu-id="a85d7-115">公共语言运行时 (CLR) 实现与托管其垃圾回收机制<xref:System.GC>类型。</span><span class="sxs-lookup"><span data-stu-id="a85d7-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="a85d7-116">有关垃圾回收系统的详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a85d7-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a85d7-117">惠?</span><span class="sxs-lookup"><span data-stu-id="a85d7-117">Requirements</span></span>  
 <span data-ttu-id="a85d7-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a85d7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a85d7-119">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a85d7-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a85d7-120">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a85d7-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a85d7-121">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a85d7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a85d7-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a85d7-122">See Also</span></span>  
 [<span data-ttu-id="a85d7-123">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="a85d7-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="a85d7-124">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="a85d7-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="a85d7-125">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="a85d7-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="a85d7-126">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="a85d7-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="a85d7-127">承载接口</span><span class="sxs-lookup"><span data-stu-id="a85d7-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="a85d7-128">承载</span><span class="sxs-lookup"><span data-stu-id="a85d7-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
