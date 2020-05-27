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
ms.openlocfilehash: 9d6c9d22f4e50c21e2f41b7efd402907ff5843db
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805218"
---
# <a name="igchost-interface"></a><span data-ttu-id="b425a-102">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="b425a-102">IGCHost Interface</span></span>
<span data-ttu-id="b425a-103">提供一些方法，用于获取有关垃圾回收系统的信息并控制垃圾回收的某些方面。</span><span class="sxs-lookup"><span data-stu-id="b425a-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b425a-104">从 .NET Framework 4.5 开始，你可以使用[IGCHost2：： SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法将垃圾回收段的大小和垃圾回收系统的第0代的最大大小设置为大于 `DWORD` [SetGCStartupLimits](igchost-setgcstartuplimits-method.md)方法施加的限制的值。</span><span class="sxs-lookup"><span data-stu-id="b425a-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b425a-105">此接口仅供专家使用。</span><span class="sxs-lookup"><span data-stu-id="b425a-105">This interface is for expert usage only.</span></span> <span data-ttu-id="b425a-106">如果使用不当，可能会影响应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="b425a-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b425a-107">方法</span><span class="sxs-lookup"><span data-stu-id="b425a-107">Methods</span></span>  
  
|<span data-ttu-id="b425a-108">方法</span><span class="sxs-lookup"><span data-stu-id="b425a-108">Method</span></span>|<span data-ttu-id="b425a-109">说明</span><span class="sxs-lookup"><span data-stu-id="b425a-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b425a-110">Collect 方法</span><span class="sxs-lookup"><span data-stu-id="b425a-110">Collect Method</span></span>](igchost-collect-method.md)|<span data-ttu-id="b425a-111">为给定的生成强制执行回收，而不考虑当前垃圾回收的状态。</span><span class="sxs-lookup"><span data-stu-id="b425a-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="b425a-112">GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="b425a-112">GetStats Method</span></span>](igchost-getstats-method.md)|<span data-ttu-id="b425a-113">获取垃圾收集系统的当前状态的统计信息。</span><span class="sxs-lookup"><span data-stu-id="b425a-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="b425a-114">GetThreadStats 方法</span><span class="sxs-lookup"><span data-stu-id="b425a-114">GetThreadStats Method</span></span>](igchost-getthreadstats-method.md)|<span data-ttu-id="b425a-115">获取用于垃圾回收的每个线程的统计信息。</span><span class="sxs-lookup"><span data-stu-id="b425a-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="b425a-116">SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="b425a-116">SetGCStartupLimits Method</span></span>](igchost-setgcstartuplimits-method.md)|<span data-ttu-id="b425a-117">设置第0代的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="b425a-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="b425a-118">SetVirtualMemLimit 方法</span><span class="sxs-lookup"><span data-stu-id="b425a-118">SetVirtualMemLimit Method</span></span>](igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="b425a-119">设置运行时的虚拟内存的最大大小。</span><span class="sxs-lookup"><span data-stu-id="b425a-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b425a-120">要求</span><span class="sxs-lookup"><span data-stu-id="b425a-120">Requirements</span></span>  
 <span data-ttu-id="b425a-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b425a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b425a-122">**标头：** GCHost，GCHost</span><span class="sxs-lookup"><span data-stu-id="b425a-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b425a-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b425a-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b425a-124">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b425a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b425a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b425a-125">See also</span></span>

- [<span data-ttu-id="b425a-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="b425a-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b425a-127">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="b425a-127">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
