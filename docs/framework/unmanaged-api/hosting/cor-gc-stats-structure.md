---
title: "COR_GC_STATS 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_STATS
helpviewer_keywords: COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02a775be4976760b354a492e7252a67ef04eace9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corgcstats-structure"></a>COR_GC_STATS 结构
提供有关垃圾回收机制的公共语言运行时 (CLR) 的统计信息。  
  
## <a name="syntax"></a>语法  
  
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
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`Flags`|指示应计算并返回的字段值。|  
|`ExplicitGCCount`|指示已强制外部请求进行的垃圾回收数。|  
|`GenCollectionsTaken`|指示对于每个生成的执行的垃圾回收数。|  
|`CommittedKBytes`|总在所有的堆中提交的字节数。|  
|`ReservedKBytes`|总保留所有的堆中的字节数。|  
|`Gen0HeapSizeKBytes`|大小，以千字节为单位，零代堆。|  
|`Gen1HeapSizeKBytes`|大小，以千字节为单位，第一代堆。|  
|`Gen2HeapSizeKBytes`|大小，以千字节为单位，生成两个堆。|  
|`LargeObjectHeapSizeKBytes`|大小，以千字节为单位，大型对象堆。|  
|`KBytesPromotedFromGen0`|大小，以千字节为单位，从第 0 代提升到第一代的对象。|  
|`KBytesPromotedFromGen1`|大小，以千字节为单位，从第一代提升到第 2 代的对象。|  
  
## <a name="remarks"></a>备注  
 [Iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)方法需要`Flags`字段`COR_GC_STATS`结构将设置为一个或多个值的[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)枚举，以指定的将统计信息设置。  
  
 下表将映射到两个此结构提供的统计信息[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)枚举值`COR_GC_COUNTS`和`COR_GC_MEMORYUSAGE`。  
  
|指定 COR_GC_COUNTS|指定 COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 使用情况的一个示例是，如下所示：  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost.idl  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载结构](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [自动内存管理](../../../../docs/standard/automatic-memory-management.md)  
 [垃圾回收](../../../../docs/standard/garbage-collection/index.md)
