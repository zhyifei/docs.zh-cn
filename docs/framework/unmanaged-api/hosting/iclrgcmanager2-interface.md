---
title: ICLRGCManager2 接口
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a89a7ef34418163d790fd055de681c1cdf989e57
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226906"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="71857-102">ICLRGCManager2 接口</span><span class="sxs-lookup"><span data-stu-id="71857-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="71857-103">提供允许主机与公共语言运行时的垃圾回收系统进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="71857-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71857-104">方法</span><span class="sxs-lookup"><span data-stu-id="71857-104">Methods</span></span>  
  
|<span data-ttu-id="71857-105">方法</span><span class="sxs-lookup"><span data-stu-id="71857-105">Method</span></span>|<span data-ttu-id="71857-106">描述</span><span class="sxs-lookup"><span data-stu-id="71857-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71857-107">SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="71857-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="71857-108">设置垃圾回收段的大小和第 0 代垃圾回收系统的最大大小。</span><span class="sxs-lookup"><span data-stu-id="71857-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="71857-109">使第 0 代和段大小大于`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="71857-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71857-110">备注</span><span class="sxs-lookup"><span data-stu-id="71857-110">Remarks</span></span>  
 <span data-ttu-id="71857-111">此接口继承自[ICLRGCManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="71857-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="71857-112">公共语言运行时 (CLR) 实现与托管其垃圾回收机制<xref:System.GC>类型。</span><span class="sxs-lookup"><span data-stu-id="71857-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="71857-113">有关垃圾回收系统的详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="71857-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71857-114">要求</span><span class="sxs-lookup"><span data-stu-id="71857-114">Requirements</span></span>  
 <span data-ttu-id="71857-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71857-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71857-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71857-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71857-117">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="71857-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="71857-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="71857-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="71857-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="71857-119">See also</span></span>

- [<span data-ttu-id="71857-120">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="71857-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="71857-121">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="71857-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="71857-122">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="71857-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="71857-123">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="71857-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="71857-124">承载接口</span><span class="sxs-lookup"><span data-stu-id="71857-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="71857-125">宿主</span><span class="sxs-lookup"><span data-stu-id="71857-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
