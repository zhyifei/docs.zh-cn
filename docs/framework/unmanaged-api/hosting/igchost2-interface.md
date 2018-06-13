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
ms.openlocfilehash: 5c6cbf44bd02a45b9b99d2dad63fc5bd6219c4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437672"
---
# <a name="igchost2-interface"></a><span data-ttu-id="35bf2-102">IGCHost2 接口</span><span class="sxs-lookup"><span data-stu-id="35bf2-102">IGCHost2 Interface</span></span>
<span data-ttu-id="35bf2-103">提供用于获取有关垃圾回收系统的信息以及控制垃圾回收的某些方面的方法。</span><span class="sxs-lookup"><span data-stu-id="35bf2-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35bf2-104">对于新开发，我们建议你使用[ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="35bf2-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35bf2-105">方法</span><span class="sxs-lookup"><span data-stu-id="35bf2-105">Methods</span></span>  
  
|<span data-ttu-id="35bf2-106">方法</span><span class="sxs-lookup"><span data-stu-id="35bf2-106">Method</span></span>|<span data-ttu-id="35bf2-107">描述</span><span class="sxs-lookup"><span data-stu-id="35bf2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35bf2-108">SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="35bf2-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="35bf2-109">为第 0 代中设置的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="35bf2-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="35bf2-110">使第 0 代和段大小大于`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="35bf2-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35bf2-111">要求</span><span class="sxs-lookup"><span data-stu-id="35bf2-111">Requirements</span></span>  
 <span data-ttu-id="35bf2-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35bf2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35bf2-113">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="35bf2-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="35bf2-114">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="35bf2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35bf2-115">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35bf2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35bf2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="35bf2-116">See Also</span></span>  
 [<span data-ttu-id="35bf2-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="35bf2-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="35bf2-118">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="35bf2-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="35bf2-119">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="35bf2-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
