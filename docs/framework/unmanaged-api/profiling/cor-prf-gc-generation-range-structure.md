---
title: "COR_PRF_GC_GENERATION_RANGE 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_GENERATION_RANGE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords: COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59969f45d4cca0ff208bd9e77c93994cad61ab13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcgenerationrange-structure"></a>COR_PRF_GC_GENERATION_RANGE 结构
描述一个正进行垃圾回收的内存范围（即块）。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`generation`|值为[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)所属指定的内存块的与其生成的枚举。|  
|`rangeStart`|一个指定的内存块的起始位置的对象的 ID。|  
|`rangeLength`|指向一个整数，指定的内存块 （即，在块中使用的内存量） 已使用部分大小的指针。|  
|`rangeLengthReserved`|指向一个整数，指定内存块 （即块保留的内存量） 的大小的指针。|  
  
## <a name="remarks"></a>备注  
 `rangeLength`值一定要准确才[icorprofilerinfo2:: Getgenerationbounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)或[icorprofilerinfo2:: Getobjectgeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)，这两个使用`COR_PRF_GC_GENERATION_RANGE`结构，请从调用[icorprofilercallback2:: Garbagecollectionstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)或[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [分析结构](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
