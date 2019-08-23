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
ms.openlocfilehash: 76d1071ddde1509f16fd786afa4c05c05224d051
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966213"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="1914a-102">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="1914a-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="1914a-103">提供允许主机与公共语言运行时的垃圾回收系统交互的方法。</span><span class="sxs-lookup"><span data-stu-id="1914a-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1914a-104">从 .NET Framework 4.5 开始, 可以使用[ICLRGCManager2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法将垃圾回收段的大小和垃圾回收系统的0代的最大大小设置为大于的`DWORD`值。 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)方法强加的限制。</span><span class="sxs-lookup"><span data-stu-id="1914a-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1914a-105">方法</span><span class="sxs-lookup"><span data-stu-id="1914a-105">Methods</span></span>  
  
|<span data-ttu-id="1914a-106">方法</span><span class="sxs-lookup"><span data-stu-id="1914a-106">Method</span></span>|<span data-ttu-id="1914a-107">描述</span><span class="sxs-lookup"><span data-stu-id="1914a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1914a-108">Collect 方法</span><span class="sxs-lookup"><span data-stu-id="1914a-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="1914a-109">强制执行指定代的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="1914a-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="1914a-110">GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="1914a-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="1914a-111">获取有关垃圾回收系统的当前统计信息集。</span><span class="sxs-lookup"><span data-stu-id="1914a-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="1914a-112">SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="1914a-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="1914a-113">设置垃圾回收段的大小以及垃圾回收系统的第0代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="1914a-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1914a-114">备注</span><span class="sxs-lookup"><span data-stu-id="1914a-114">Remarks</span></span>  
 <span data-ttu-id="1914a-115">公共语言运行时 (CLR) 实现了托管<xref:System.GC>类型的垃圾回收机制。</span><span class="sxs-lookup"><span data-stu-id="1914a-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="1914a-116">有关垃圾回收系统的详细信息, 请参阅[垃圾](../../../standard/garbage-collection/index.md)回收。</span><span class="sxs-lookup"><span data-stu-id="1914a-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1914a-117">要求</span><span class="sxs-lookup"><span data-stu-id="1914a-117">Requirements</span></span>  
 <span data-ttu-id="1914a-118">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1914a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1914a-119">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1914a-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1914a-120">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1914a-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1914a-121">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1914a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1914a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="1914a-122">See also</span></span>

- [<span data-ttu-id="1914a-123">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="1914a-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="1914a-124">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="1914a-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="1914a-125">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="1914a-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1914a-126">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="1914a-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="1914a-127">承载接口</span><span class="sxs-lookup"><span data-stu-id="1914a-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1914a-128">承载</span><span class="sxs-lookup"><span data-stu-id="1914a-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
