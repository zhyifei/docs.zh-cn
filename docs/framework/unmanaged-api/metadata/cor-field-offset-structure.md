---
title: "COR_FIELD_OFFSET 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_FIELD_OFFSET
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_FIELD_OFFSET
helpviewer_keywords: COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed41538ae4c1e70843c613493eee9d632dff5f91
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corfieldoffset-structure"></a>COR_FIELD_OFFSET 结构
存储一个类中的指定字段的偏移量。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`ridOfField`|`mdFieldDef`元数据标记表示的字段。|  
|`ulOffset`|在它的类情况下，字段的偏移量。|  
  
## <a name="remarks"></a>备注  
 [Imetadataimport:: Getclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md)和[imetadataemit:: Setclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)方法接受类型的参数`COR_FIELD_OFFSET`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h、 CorProf.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据结构](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
