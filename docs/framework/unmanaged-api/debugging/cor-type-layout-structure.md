---
title: "COR_TYPE_LAYOUT 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPE_LAYOUT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPE_LAYOUT
helpviewer_keywords: COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 250d78dd9983b75fa7e1b3cfd99215160fbc2b1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cortypelayout-structure"></a>COR_TYPE_LAYOUT 结构
提供有关内存中某个对象的布局的信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`parentID`|为此类型的父类型的标识符。 这将是 NULL 类型 id (token1 = 0，token2 = 0) 如果类型 id 对应于<xref:System.Object?displayProperty=nameWithType>。|  
|`objectSize`|此类型的对象的基大小。 这是非变量大小对象的总大小。|  
|`numFields`|此类型的对象中包含的字段数。|  
|`boxOffset`|如果此类型进行装箱时，对象的字段的偏移量开始。 此字段为仅对值类型，如基元和结构有效。|  
|`type`|此类型属于 CorElementType。|  
  
## <a name="remarks"></a>备注  
 如果`numFields`大于零，可以调用[icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)方法来获取有关此类型中的字段的信息。 如果`type`是`ELEMENT_TYPE_STRING`， `ELEMENT_TYPE_ARRAY`，或`ELEMENT_TYPE_SZARRAY`，此类型的对象的大小是变量，并且可以通过[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)结构[icordebugprocess5:: Getarraylayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
