---
title: "COR_PRF_GC_GENERATION 枚举"
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
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69eec0c2dfccacee4c54c9f2493da523812259aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcgeneration-enumeration"></a>COR_PRF_GC_GENERATION 枚举
标识垃圾回收生成。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|为第 0 代存储对象。|  
|`COR_PRF_GC_GEN_1`|为第 1 代存储对象。|  
|`COR_PRF_GC_GEN_2`|作为第 2 代存储对象。|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|大型对象堆中存储对象。|  
  
## <a name="remarks"></a>备注  
 垃圾回收器内存管理性能提高将对象划分为不同的代根据存在时间。 垃圾回收器当前正在使用三代，编号为 0、 1 和 2，以及用于大型对象的特殊堆段。 其大小大于特定值的对象存储在大型对象堆。 其他分配的对象都属于第 0 代。 第 0 代中发生了垃圾回收后存在的所有对象将被都提升到第 1 代中。 第 1 代中发生了垃圾回收后存在的对象将移到第 2 代。  
  
 代意味着垃圾回收器必须使用分配的对象的一个子集在任何时候使用。  
  
 `COR_PRF_GC_GENERATION`枚举由[COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)结构。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
