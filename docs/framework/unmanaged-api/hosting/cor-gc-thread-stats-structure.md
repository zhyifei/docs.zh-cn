---
title: COR_GC_THREAD_STATS 结构
ms.date: 03/30/2017
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
ms.openlocfilehash: 37da471aaa8e9f802a8430d7b3289b375ff1b40a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136985"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="d5387-102">COR_GC_THREAD_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="d5387-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="d5387-103">包含与垃圾回收相关的每个线程的统计信息。</span><span class="sxs-lookup"><span data-stu-id="d5387-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5387-104">语法</span><span class="sxs-lookup"><span data-stu-id="d5387-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="d5387-105">Members</span><span class="sxs-lookup"><span data-stu-id="d5387-105">Members</span></span>  
  
|<span data-ttu-id="d5387-106">成员</span><span class="sxs-lookup"><span data-stu-id="d5387-106">Member</span></span>|<span data-ttu-id="d5387-107">描述</span><span class="sxs-lookup"><span data-stu-id="d5387-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="d5387-108">与当前 `COR_GC_THREAD_STATS` 实例相关联的线程上分配的内存字节数。</span><span class="sxs-lookup"><span data-stu-id="d5387-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="d5387-109">每次发生零代垃圾回收时，此数字会被清除为零。</span><span class="sxs-lookup"><span data-stu-id="d5387-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="d5387-110">最近一次垃圾回收后提升为较高代的字节数。</span><span class="sxs-lookup"><span data-stu-id="d5387-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5387-111">备注</span><span class="sxs-lookup"><span data-stu-id="d5387-111">Remarks</span></span>  
 <span data-ttu-id="d5387-112">[ICLRTask：： GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)使用 `COR_GC_THREAD_STATS`类型的输出参数。</span><span class="sxs-lookup"><span data-stu-id="d5387-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5387-113">要求</span><span class="sxs-lookup"><span data-stu-id="d5387-113">Requirements</span></span>  
 <span data-ttu-id="d5387-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5387-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5387-115">**标头：** GCHost .idl</span><span class="sxs-lookup"><span data-stu-id="d5387-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="d5387-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d5387-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5387-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5387-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5387-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5387-118">See also</span></span>

- [<span data-ttu-id="d5387-119">承载结构</span><span class="sxs-lookup"><span data-stu-id="d5387-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="d5387-120">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="d5387-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
