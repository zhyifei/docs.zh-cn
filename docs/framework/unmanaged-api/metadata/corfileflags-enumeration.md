---
title: CorFileFlags 枚举
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
ms.openlocfilehash: c315e2ae2753b59b4e277764d27c3fb3388b515c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445417"
---
# <a name="corfileflags-enumeration"></a>CorFileFlags 枚举
包含一些值，这些值描述在对[IMetaDataAssemblyEmit：:D efinefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)的调用中定义的文件类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`ffContainsMetaData`|指示该文件不是资源文件。|  
|`ffContainsNoMetaData`|指示文件可能不包含元数据，可能是资源文件。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corhdr。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
