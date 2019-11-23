---
title: CorErrorIfEmitOutOfOrder 枚举
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: 57460ba30a8ce974b5ca89f76796c4dcf49ffecf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443582"
---
# <a name="corerrorifemitoutoforder-enumeration"></a>CorErrorIfEmitOutOfOrder 枚举
包含一些标志值，用于指示无序发出元数据时应生成错误消息的条件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Indicates the default behavior, which does not generate error messages.|  
|`MDErrorOutOfOrderNone`|Indicates that the compiler should not generate error messages.|  
|`MDErrorOutOfOrderAll`|Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.|  
|`MDMethodOutOfOrder`|Indicates that the compiler should generate an error message when a method is emitted out of order.|  
|`MDFieldOutOfOrder`|Indicates that the compiler should generate an error message when a field is emitted out of order.|  
|`MDParamOutOfOrder`|Indicates that the compiler should generate an error message when a parameter is emitted out of order.|  
|`MDPropertyOutOfOrder`|Indicates that the compiler should generate an error message when a property is emitted out of order.|  
|`MDEventOutOfOrder`|Indicates that the compiler should generate an error message when an event is emitted out of order.|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **Header:** CorHdr.h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
