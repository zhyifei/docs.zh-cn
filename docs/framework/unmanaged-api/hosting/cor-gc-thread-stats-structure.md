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
ms.openlocfilehash: 64e0c466edcd8863244e6ed184c18422b5f66875
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178271"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="cede3-102">COR_GC_THREAD_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="cede3-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="cede3-103">包含与垃圾回收相关的每个线程统计信息。</span><span class="sxs-lookup"><span data-stu-id="cede3-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cede3-104">语法</span><span class="sxs-lookup"><span data-stu-id="cede3-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="cede3-105">成员</span><span class="sxs-lookup"><span data-stu-id="cede3-105">Members</span></span>  
  
|<span data-ttu-id="cede3-106">成员</span><span class="sxs-lookup"><span data-stu-id="cede3-106">Member</span></span>|<span data-ttu-id="cede3-107">说明</span><span class="sxs-lookup"><span data-stu-id="cede3-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="cede3-108">在与当前`COR_GC_THREAD_STATS`实例关联的线程上分配的内存字节数。</span><span class="sxs-lookup"><span data-stu-id="cede3-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="cede3-109">每次发生生成零垃圾回收时，此数字将清除为零。</span><span class="sxs-lookup"><span data-stu-id="cede3-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="cede3-110">在最近的垃圾回收中提升为更高一代的字节数。</span><span class="sxs-lookup"><span data-stu-id="cede3-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cede3-111">备注</span><span class="sxs-lookup"><span data-stu-id="cede3-111">Remarks</span></span>  
 <span data-ttu-id="cede3-112">[ICLR任务：getMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)采用类型的`COR_GC_THREAD_STATS`输出参数。</span><span class="sxs-lookup"><span data-stu-id="cede3-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cede3-113">要求</span><span class="sxs-lookup"><span data-stu-id="cede3-113">Requirements</span></span>  
 <span data-ttu-id="cede3-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cede3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cede3-115">**标题：** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="cede3-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="cede3-116">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="cede3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cede3-117">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cede3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cede3-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cede3-118">See also</span></span>

- [<span data-ttu-id="cede3-119">承载结构</span><span class="sxs-lookup"><span data-stu-id="cede3-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="cede3-120">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="cede3-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
