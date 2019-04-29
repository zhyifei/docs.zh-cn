---
title: ICLRGCManager 接口
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9519f7c2df5cf078bac6be038275527d7741edb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700834"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="122b8-102">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="122b8-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="122b8-103">提供允许主机与公共语言运行时的垃圾回收系统进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="122b8-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="122b8-104">从开始[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，可以使用[ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法设置为值的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小更高版本比`DWORD`施加的限制[SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="122b8-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="122b8-105">方法</span><span class="sxs-lookup"><span data-stu-id="122b8-105">Methods</span></span>  
  
|<span data-ttu-id="122b8-106">方法</span><span class="sxs-lookup"><span data-stu-id="122b8-106">Method</span></span>|<span data-ttu-id="122b8-107">描述</span><span class="sxs-lookup"><span data-stu-id="122b8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="122b8-108">Collect 方法</span><span class="sxs-lookup"><span data-stu-id="122b8-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="122b8-109">强制对指定代进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="122b8-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="122b8-110">GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="122b8-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="122b8-111">获取一组有关垃圾回收系统的当前统计信息。</span><span class="sxs-lookup"><span data-stu-id="122b8-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="122b8-112">SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="122b8-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="122b8-113">设置垃圾回收段的大小和第 0 代垃圾回收系统的最大大小。</span><span class="sxs-lookup"><span data-stu-id="122b8-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="122b8-114">备注</span><span class="sxs-lookup"><span data-stu-id="122b8-114">Remarks</span></span>  
 <span data-ttu-id="122b8-115">公共语言运行时 (CLR) 实现与托管其垃圾回收机制<xref:System.GC>类型。</span><span class="sxs-lookup"><span data-stu-id="122b8-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="122b8-116">有关垃圾回收系统的详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="122b8-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="122b8-117">要求</span><span class="sxs-lookup"><span data-stu-id="122b8-117">Requirements</span></span>  
 <span data-ttu-id="122b8-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="122b8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="122b8-119">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="122b8-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="122b8-120">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="122b8-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="122b8-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="122b8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="122b8-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="122b8-122">See also</span></span>

- [<span data-ttu-id="122b8-123">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="122b8-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="122b8-124">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="122b8-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="122b8-125">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="122b8-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="122b8-126">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="122b8-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="122b8-127">承载接口</span><span class="sxs-lookup"><span data-stu-id="122b8-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="122b8-128">承载</span><span class="sxs-lookup"><span data-stu-id="122b8-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
