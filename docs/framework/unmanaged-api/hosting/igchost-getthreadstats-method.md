---
title: IGCHost::GetThreadStats 方法
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74827fac102ee6045965f4ba9d74dd3b1aa0af86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437565"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="de781-102">IGCHost::GetThreadStats 方法</span><span class="sxs-lookup"><span data-stu-id="de781-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="de781-103">获取垃圾回收的每个线程统计信息。</span><span class="sxs-lookup"><span data-stu-id="de781-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de781-104">语法</span><span class="sxs-lookup"><span data-stu-id="de781-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de781-105">参数</span><span class="sxs-lookup"><span data-stu-id="de781-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="de781-106">[in]指向纤程 cookie，指定为其检索统计信息的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="de781-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="de781-107">[在中，out]指向的指针[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)包含指定的线程的垃圾收集统计信息的结构。</span><span class="sxs-lookup"><span data-stu-id="de781-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de781-108">要求</span><span class="sxs-lookup"><span data-stu-id="de781-108">Requirements</span></span>  
 <span data-ttu-id="de781-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de781-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de781-110">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="de781-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="de781-111">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="de781-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de781-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de781-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de781-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="de781-113">See Also</span></span>  
 [<span data-ttu-id="de781-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="de781-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
