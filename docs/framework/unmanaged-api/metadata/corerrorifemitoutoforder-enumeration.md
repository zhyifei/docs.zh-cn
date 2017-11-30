---
title: "CorErrorIfEmitOutOfOrder 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorErrorIfEmitOutOfOrder
api_location: mscoree.dll
api_type: COM
f1_keywords: CorErrorIfEmitOutOfOrder
helpviewer_keywords: CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2cf80375622912c6bb9a59696f37aed2d594253
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corerrorifemitoutoforder-enumeration"></a>CorErrorIfEmitOutOfOrder 枚举
包含一些标志值，用于指示无序发出元数据时应生成错误消息的条件。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|指示默认行为，不会生成错误消息。|  
|`MDErrorOutOfOrderNone`|指示编译器不应生成错误消息。|  
|`MDErrorOutOfOrderAll`|指示当字段、 属性、 事件、 方法时，编译器应生成一条错误消息或无序发出参数。|  
|`MDMethodOutOfOrder`|指示当无序发出方法时，编译器应生成一条错误消息。|  
|`MDFieldOutOfOrder`|指示当无序发出字段时，编译器应生成一条错误消息。|  
|`MDParamOutOfOrder`|指示当无序发出参数时，编译器应生成一条错误消息。|  
|`MDPropertyOutOfOrder`|指示当无序发出属性时，编译器应生成一条错误消息。|  
|`MDEventOutOfOrder`|指示当无序发出事件时，编译器应生成一条错误消息。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [元数据枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
