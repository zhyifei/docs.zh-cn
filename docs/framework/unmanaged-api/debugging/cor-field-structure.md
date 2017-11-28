---
title: "COR_FIELD 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_FIELD
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_FIELD
helpviewer_keywords: COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a01687b5a49bb64ab037dc408c8cc5bd381be589
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="corfield-structure"></a>COR_FIELD 结构
提供有关对象中的某个字段的信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`token`|`mdFieldDef`可以用于获取字段信息的令牌。|  
|`offset`|偏移量，以字节为单位，该对象中的字段数据。|  
|`id`|A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)值，该值标识此字段的类型。|  
|`fieldType`|CorElementType 枚举值，该值指示字段的类型。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
