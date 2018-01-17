---
title: "COR_GC_REFERENCE 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_REFERENCE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_GC_REFERENCE
helpviewer_keywords: COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a86604febb7641eef147608e564a27883fdc4bec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreference-structure"></a>COR_GC_REFERENCE 结构
包含有关要进行垃圾回收的对象的信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`domain`|指向句柄或对象所属的应用程序域的指针。 其值可能`null`。|  
|`location`|ICorDebugValue 或 ICorDebugReferenceValue 接口对应于要进行垃圾回收的对象。|  
|`type`|A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)枚举值，该值指示根来自何处。 有关详细信息，请参阅“备注”部分。|  
|`extraData`|要进行垃圾回收的对象有关的其他数据。 此信息取决于源的对象，如所示`type`字段。 有关详细信息，请参阅“备注”部分。|  
  
## <a name="remarks"></a>备注  
 `type`字段是[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)枚举值，该值指示引用来自何处。 特定`COR_GC_REFERENCE`值可以反映任何以下类型的托管对象：  
  
-   从所有托管堆栈的对象 (`CorGCReferenceType.CorReferenceStack`)。 这包括实时引用在托管的代码中，以及由公共语言运行时创建的对象。  
  
-   来自句柄表的对象 (`CorGCReferenceType.CorHandle*`)。 这包括的强引用 (`HNDTYPE_STRONG`和`HNDTYPE_REFCOUNT`) 和模块中的静态变量。  
  
-   终结器队列中的对象 (`CorGCReferenceType.CorReferenceFinalizer`)。 终结器队列根对象，直到运行终结器。  
  
 `extraData`字段包含额外的数据，具体取决于引用的源 （或类型）。 可能的值有：  
  
-   `DependentSource`。 如果`type`是`CorGCREferenceType.CorHandleStrongDependent`，此字段是对象处于活动状态，如果根对象要进行垃圾回收在`COR_GC_REFERENCE.Location`。  
  
-   `RefCount`。 如果`type`是`CorGCREferenceType.CorHandleStrongRefCount`，此字段是句柄的引用计数。  
  
-   `Size`。 如果`type`是`CorGCREferenceType.CorHandleStrongSizedByref`，此字段是垃圾回收器为其计算对象根的对象树的最后一个大小。 请注意，此计算不一定最新。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
