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
ms.openlocfilehash: 75bef91eb70c8109653741452362cd2e85f625ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138133"
---
# <a name="igchost2-interface"></a><span data-ttu-id="33923-102">IGCHost2 接口</span><span class="sxs-lookup"><span data-stu-id="33923-102">IGCHost2 Interface</span></span>
<span data-ttu-id="33923-103">提供方法用于获取有关垃圾回收系统的信息以及用于控制垃圾回收的某些方面。</span><span class="sxs-lookup"><span data-stu-id="33923-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33923-104">对于新开发，我们建议你使用[ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)改为接口。</span><span class="sxs-lookup"><span data-stu-id="33923-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33923-105">方法</span><span class="sxs-lookup"><span data-stu-id="33923-105">Methods</span></span>  
  
|<span data-ttu-id="33923-106">方法</span><span class="sxs-lookup"><span data-stu-id="33923-106">Method</span></span>|<span data-ttu-id="33923-107">描述</span><span class="sxs-lookup"><span data-stu-id="33923-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33923-108">SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="33923-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="33923-109">设置第 0 代段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="33923-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="33923-110">使第 0 代和段大小大于`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="33923-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33923-111">要求</span><span class="sxs-lookup"><span data-stu-id="33923-111">Requirements</span></span>  
 <span data-ttu-id="33923-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33923-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33923-113">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="33923-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="33923-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="33923-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="33923-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="33923-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33923-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="33923-116">See also</span></span>

- [<span data-ttu-id="33923-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="33923-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="33923-118">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="33923-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="33923-119">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="33923-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
