---
title: COR_GC_STATS 结构
ms.date: 03/30/2017
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d335a62545f06a66d4044b59aa9499d3f7ede515
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774538"
---
# <a name="corgcstats-structure"></a><span data-ttu-id="6d270-102">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="6d270-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="6d270-103">提供有关垃圾回收机制的公共语言运行时 (CLR) 的统计信息。</span><span class="sxs-lookup"><span data-stu-id="6d270-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d270-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d270-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;   
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;   
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="6d270-105">成员</span><span class="sxs-lookup"><span data-stu-id="6d270-105">Members</span></span>  
  
|<span data-ttu-id="6d270-106">成员</span><span class="sxs-lookup"><span data-stu-id="6d270-106">Member</span></span>|<span data-ttu-id="6d270-107">描述</span><span class="sxs-lookup"><span data-stu-id="6d270-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="6d270-108">指示应计算的字段值，并将其返回。</span><span class="sxs-lookup"><span data-stu-id="6d270-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="6d270-109">指示由外部请求已强制垃圾回收的数目。</span><span class="sxs-lookup"><span data-stu-id="6d270-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="6d270-110">指示为每个代所执行的垃圾回收次数。</span><span class="sxs-lookup"><span data-stu-id="6d270-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="6d270-111">提交所有堆中的千字节为单位的总数。</span><span class="sxs-lookup"><span data-stu-id="6d270-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="6d270-112">保留所有堆中的千字节为单位的总数。</span><span class="sxs-lookup"><span data-stu-id="6d270-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="6d270-113">以千字节单位零代堆大小。</span><span class="sxs-lookup"><span data-stu-id="6d270-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="6d270-114">以千字节，第一代堆的大小。</span><span class="sxs-lookup"><span data-stu-id="6d270-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="6d270-115">以千字节，第 2 代堆的大小。</span><span class="sxs-lookup"><span data-stu-id="6d270-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="6d270-116">以千字节，大型对象堆的大小。</span><span class="sxs-lookup"><span data-stu-id="6d270-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="6d270-117">大小，以千字节为单位，从第 0 代提升到第一代的对象。</span><span class="sxs-lookup"><span data-stu-id="6d270-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="6d270-118">大小，以千字节为单位，从第一代提升到第 2 代的对象。</span><span class="sxs-lookup"><span data-stu-id="6d270-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d270-119">备注</span><span class="sxs-lookup"><span data-stu-id="6d270-119">Remarks</span></span>  
 <span data-ttu-id="6d270-120">[Iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)方法需要`Flags`字段`COR_GC_STATS`设置为一个或多个值的结构[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)枚举来指定该统计信息是设置。</span><span class="sxs-lookup"><span data-stu-id="6d270-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="6d270-121">下表将映射到两个此结构提供的统计信息[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)枚举值`COR_GC_COUNTS`和`COR_GC_MEMORYUSAGE`。</span><span class="sxs-lookup"><span data-stu-id="6d270-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="6d270-122">指定的 COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="6d270-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="6d270-123">指定的 COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="6d270-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="6d270-124">该用法的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d270-124">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="6d270-125">要求</span><span class="sxs-lookup"><span data-stu-id="6d270-125">Requirements</span></span>  
 <span data-ttu-id="6d270-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d270-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d270-127">**标头：** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="6d270-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="6d270-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6d270-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d270-129">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d270-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d270-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d270-130">See also</span></span>

- [<span data-ttu-id="6d270-131">承载结构</span><span class="sxs-lookup"><span data-stu-id="6d270-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="6d270-132">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="6d270-132">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="6d270-133">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="6d270-133">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
