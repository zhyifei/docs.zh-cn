---
title: IGCHost2 接口
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21ce9cbd007858c0f39e12622eff819154ab83f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928619"
---
# <a name="igchost2-interface"></a><span data-ttu-id="106a8-102">IGCHost2 接口</span><span class="sxs-lookup"><span data-stu-id="106a8-102">IGCHost2 Interface</span></span>
<span data-ttu-id="106a8-103">提供一些方法, 用于获取有关垃圾回收系统的信息并控制垃圾回收的某些方面。</span><span class="sxs-lookup"><span data-stu-id="106a8-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="106a8-104">对于新开发, 建议改为使用[ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="106a8-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="106a8-105">方法</span><span class="sxs-lookup"><span data-stu-id="106a8-105">Methods</span></span>  
  
|<span data-ttu-id="106a8-106">方法</span><span class="sxs-lookup"><span data-stu-id="106a8-106">Method</span></span>|<span data-ttu-id="106a8-107">描述</span><span class="sxs-lookup"><span data-stu-id="106a8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="106a8-108">SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="106a8-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="106a8-109">设置第0代的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="106a8-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="106a8-110">启用0代和大于`DWORD`的段大小。</span><span class="sxs-lookup"><span data-stu-id="106a8-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="106a8-111">要求</span><span class="sxs-lookup"><span data-stu-id="106a8-111">Requirements</span></span>  
 <span data-ttu-id="106a8-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="106a8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="106a8-113">**标头：** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="106a8-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="106a8-114">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="106a8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="106a8-115">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="106a8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106a8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="106a8-116">See also</span></span>

- [<span data-ttu-id="106a8-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="106a8-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="106a8-118">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="106a8-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="106a8-119">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="106a8-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
