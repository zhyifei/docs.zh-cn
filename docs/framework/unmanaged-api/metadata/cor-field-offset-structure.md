---
title: COR_FIELD_OFFSET 结构
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
ms.openlocfilehash: 70fb637cd1edf81be140b0e3306e3b0a483653a6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007983"
---
# <a name="cor_field_offset-structure"></a>COR_FIELD_OFFSET 结构
存储一个类中的指定字段的偏移量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`ridOfField`|`mdFieldDef`表示字段的元数据标记。|  
|`ulOffset`|字段在其类中的偏移量。|  
  
## <a name="remarks"></a>备注  
 [IMetaDataImport：： GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md)和[IMetaDataEmit：： SetClassLayout](imetadataemit-setclasslayout-method.md)方法采用类型的参数 `COR_FIELD_OFFSET` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Corhdr.h，Corprof.idl  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据结构](metadata-structures.md)
- [IMetaDataEmit 接口](imetadataemit-interface.md)
- [IMetaDataImport 接口](imetadataimport-interface.md)
