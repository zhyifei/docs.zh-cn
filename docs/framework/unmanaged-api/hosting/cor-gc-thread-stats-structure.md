---
title: "COR_GC_THREAD_STATS 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 266352984cf50dc906e77598e8dcc9216526ce17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="57491-102">COR_GC_THREAD_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="57491-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="57491-103">包含有关垃圾回收的每个线程统计信息。</span><span class="sxs-lookup"><span data-stu-id="57491-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57491-104">语法</span><span class="sxs-lookup"><span data-stu-id="57491-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="57491-105">成员</span><span class="sxs-lookup"><span data-stu-id="57491-105">Members</span></span>  
  
|<span data-ttu-id="57491-106">成员</span><span class="sxs-lookup"><span data-stu-id="57491-106">Member</span></span>|<span data-ttu-id="57491-107">描述</span><span class="sxs-lookup"><span data-stu-id="57491-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="57491-108">与当前关联的线程上分配的内存的字节数`COR_GC_THREAD_STATS`实例。</span><span class="sxs-lookup"><span data-stu-id="57491-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="57491-109">此数字将清零每次生成零垃圾回收发生时。</span><span class="sxs-lookup"><span data-stu-id="57491-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="57491-110">提升的字节数为较高代的最新的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="57491-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57491-111">备注</span><span class="sxs-lookup"><span data-stu-id="57491-111">Remarks</span></span>  
 <span data-ttu-id="57491-112">[Iclrtask:: Getmemstats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)采用类型的输出参数`COR_GC_THREAD_STATS`。</span><span class="sxs-lookup"><span data-stu-id="57491-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57491-113">惠?</span><span class="sxs-lookup"><span data-stu-id="57491-113">Requirements</span></span>  
 <span data-ttu-id="57491-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="57491-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57491-115">**标头：** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="57491-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="57491-116">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="57491-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57491-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57491-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57491-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="57491-118">See Also</span></span>  
 [<span data-ttu-id="57491-119">承载结构</span><span class="sxs-lookup"><span data-stu-id="57491-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="57491-120">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="57491-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
