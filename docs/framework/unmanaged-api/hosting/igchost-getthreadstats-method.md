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
ms.openlocfilehash: 88f86385ba4f4186d14994a2028ee11c42127546
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108339"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="47470-102">IGCHost::GetThreadStats 方法</span><span class="sxs-lookup"><span data-stu-id="47470-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="47470-103">获取垃圾回收的每个线程统计信息。</span><span class="sxs-lookup"><span data-stu-id="47470-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47470-104">语法</span><span class="sxs-lookup"><span data-stu-id="47470-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47470-105">参数</span><span class="sxs-lookup"><span data-stu-id="47470-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="47470-106">[in]指定要为其检索统计信息的线程的纤程 cookie 指向的指针。</span><span class="sxs-lookup"><span data-stu-id="47470-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="47470-107">[in、 out]一个指向[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)结构，其中包含指定的线程的垃圾收集统计信息。</span><span class="sxs-lookup"><span data-stu-id="47470-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47470-108">要求</span><span class="sxs-lookup"><span data-stu-id="47470-108">Requirements</span></span>  
 <span data-ttu-id="47470-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47470-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47470-110">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="47470-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="47470-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="47470-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="47470-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="47470-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="47470-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="47470-113">See also</span></span>

- [<span data-ttu-id="47470-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="47470-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
