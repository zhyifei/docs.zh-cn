---
title: "IGCHost2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost2
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost2
helpviewer_keywords: IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c6706696e3fd5158d2b49a4d114d978a26510b67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="igchost2-interface"></a><span data-ttu-id="36c08-102">IGCHost2 接口</span><span class="sxs-lookup"><span data-stu-id="36c08-102">IGCHost2 Interface</span></span>
<span data-ttu-id="36c08-103">提供用于获取有关垃圾回收系统的信息以及控制垃圾回收的某些方面的方法。</span><span class="sxs-lookup"><span data-stu-id="36c08-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36c08-104">对于新开发，我们建议你使用[ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="36c08-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36c08-105">方法</span><span class="sxs-lookup"><span data-stu-id="36c08-105">Methods</span></span>  
  
|<span data-ttu-id="36c08-106">方法</span><span class="sxs-lookup"><span data-stu-id="36c08-106">Method</span></span>|<span data-ttu-id="36c08-107">描述</span><span class="sxs-lookup"><span data-stu-id="36c08-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36c08-108">SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="36c08-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="36c08-109">为第 0 代中设置的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="36c08-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="36c08-110">使第 0 代和段大小大于`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="36c08-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36c08-111">要求</span><span class="sxs-lookup"><span data-stu-id="36c08-111">Requirements</span></span>  
 <span data-ttu-id="36c08-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36c08-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c08-113">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="36c08-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="36c08-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="36c08-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36c08-115">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36c08-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c08-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36c08-116">See Also</span></span>  
 [<span data-ttu-id="36c08-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="36c08-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="36c08-118">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="36c08-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="36c08-119">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="36c08-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
