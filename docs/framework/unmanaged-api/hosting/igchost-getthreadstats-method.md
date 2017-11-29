---
title: "IGCHost::GetThreadStats 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetThreadStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7bfd6b89c3220e071a477e0c5b85e4ee57289762
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="18a20-102">IGCHost::GetThreadStats 方法</span><span class="sxs-lookup"><span data-stu-id="18a20-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="18a20-103">获取垃圾回收的每个线程统计信息。</span><span class="sxs-lookup"><span data-stu-id="18a20-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a20-104">语法</span><span class="sxs-lookup"><span data-stu-id="18a20-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18a20-105">参数</span><span class="sxs-lookup"><span data-stu-id="18a20-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="18a20-106">[in]指向纤程 cookie，指定为其检索统计信息的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="18a20-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="18a20-107">[在中，out]指向的指针[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)包含指定的线程的垃圾收集统计信息的结构。</span><span class="sxs-lookup"><span data-stu-id="18a20-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18a20-108">要求</span><span class="sxs-lookup"><span data-stu-id="18a20-108">Requirements</span></span>  
 <span data-ttu-id="18a20-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18a20-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18a20-110">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="18a20-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="18a20-111">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="18a20-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18a20-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18a20-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a20-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18a20-113">See Also</span></span>  
 [<span data-ttu-id="18a20-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="18a20-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
