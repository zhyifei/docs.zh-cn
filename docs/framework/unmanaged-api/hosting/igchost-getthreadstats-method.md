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
ms.openlocfilehash: 4a7a2da58e197749d492f24c7a12134508efef57
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805233"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="c88d8-102">IGCHost::GetThreadStats 方法</span><span class="sxs-lookup"><span data-stu-id="c88d8-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="c88d8-103">获取用于垃圾回收的每个线程的统计信息。</span><span class="sxs-lookup"><span data-stu-id="c88d8-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c88d8-104">语法</span><span class="sxs-lookup"><span data-stu-id="c88d8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c88d8-105">参数</span><span class="sxs-lookup"><span data-stu-id="c88d8-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="c88d8-106">中指向指定要检索其统计信息的线程的纤程 cookie 的指针。</span><span class="sxs-lookup"><span data-stu-id="c88d8-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="c88d8-107">[in，out]指向[COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md)结构的指针，该结构包含指定线程的垃圾回收统计信息。</span><span class="sxs-lookup"><span data-stu-id="c88d8-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c88d8-108">要求</span><span class="sxs-lookup"><span data-stu-id="c88d8-108">Requirements</span></span>  
 <span data-ttu-id="c88d8-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c88d8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c88d8-110">**标头：** GCHost，GCHost</span><span class="sxs-lookup"><span data-stu-id="c88d8-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="c88d8-111">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c88d8-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c88d8-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c88d8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88d8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c88d8-113">See also</span></span>

- [<span data-ttu-id="c88d8-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="c88d8-114">IGCHost Interface</span></span>](igchost-interface.md)
