---
title: "IDENTITY_ATTRIBUTE 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IDENTITY_ATTRIBUTE
helpviewer_keywords: IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3fc4d9f7a95a3283d87f036163592f43e87dd053
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="identityattribute-structure"></a>IDENTITY_ATTRIBUTE 结构
包含有关的元数据特性信息[IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)实例。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`pszNamespace`|属性是在指向包含的命名空间的以 null 结尾的字符字符串的指针。|  
|`pszName`|指向包含属性的名称的以 null 结尾的字符字符串的指针。|  
|`pszValue`|指向包含属性的值的以 null 结尾的字符字符串的指针。|  
  
## <a name="remarks"></a>备注  
 `IDENTITY_ATTRIBUTE`结构包含三个指针指向以 null 结尾的字符字符串。 这三个字符串描述一个属性。  
  
 实例`IDENTITY_ATTRIBUTE`结构是与实例相关联[IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)结构。 `IDENTITY_ATTRIBUTE`结构包含实际的字符串，并相应`IDENTITY_ATTRIBUTE_BLOB`结构列出的三个字符串中列出的偏移量`IDENTITY_ATTRIBUTE`结构。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IDefinitionIdentity 接口](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [IDENTITY_ATTRIBUTE_BLOB 结构](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [合成结构](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
