---
title: IGCHost 接口
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 167e2477e5185112408793e145bc5a4fabea7fc8
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377617"
---
# <a name="igchost-interface"></a><span data-ttu-id="3cbd4-102">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="3cbd4-102">IGCHost Interface</span></span>
<span data-ttu-id="3cbd4-103">提供方法用于获取有关垃圾回收系统的信息以及用于控制垃圾回收的某些方面。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cbd4-104">从.NET Framework 4.5 开始，你可以使用[IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法设置为值的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小大于`DWORD`施加的限制[SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cbd4-105">此接口是仅供专家使用。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-105">This interface is for expert usage only.</span></span> <span data-ttu-id="3cbd4-106">如果使用不当，它会影响应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3cbd4-107">方法</span><span class="sxs-lookup"><span data-stu-id="3cbd4-107">Methods</span></span>  
  
|<span data-ttu-id="3cbd4-108">方法</span><span class="sxs-lookup"><span data-stu-id="3cbd4-108">Method</span></span>|<span data-ttu-id="3cbd4-109">描述</span><span class="sxs-lookup"><span data-stu-id="3cbd4-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3cbd4-110">Collect 方法</span><span class="sxs-lookup"><span data-stu-id="3cbd4-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="3cbd4-111">强制给定生成，而不考虑当前的垃圾回收状态发生的集合。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="3cbd4-112">GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="3cbd4-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="3cbd4-113">获取垃圾回收系统的当前状态的统计信息。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="3cbd4-114">GetThreadStats 方法</span><span class="sxs-lookup"><span data-stu-id="3cbd4-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="3cbd4-115">获取垃圾回收的每个线程统计信息。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="3cbd4-116">SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="3cbd4-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="3cbd4-117">设置第 0 代段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="3cbd4-118">SetVirtualMemLimit 方法</span><span class="sxs-lookup"><span data-stu-id="3cbd4-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="3cbd4-119">设置运行时的虚拟内存的最大大小。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3cbd4-120">要求</span><span class="sxs-lookup"><span data-stu-id="3cbd4-120">Requirements</span></span>  
 <span data-ttu-id="3cbd4-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3cbd4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cbd4-122">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="3cbd4-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="3cbd4-123">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3cbd4-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cbd4-124">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbd4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cbd4-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cbd4-125">See also</span></span>

- [<span data-ttu-id="3cbd4-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="3cbd4-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="3cbd4-127">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="3cbd4-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
