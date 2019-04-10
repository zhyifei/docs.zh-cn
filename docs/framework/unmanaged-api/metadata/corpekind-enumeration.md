---
title: CorPEKind 枚举
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8f830ca7e273b65dc9ec77566a02df6c32cd464
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202386"
---
# <a name="corpekind-enumeration"></a>CorPEKind 枚举
包含值，用于描述一个可移植可执行 (PE) 文件，如从调用返回[IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`peNot`|指示这不是 PE 文件。|  
|`peILOnly`|指示此 PE 文件包含仅托管代码。|  
|`pe32BitRequired`|指示此 PE 文件进行 Win32 调用。|  
|`pe32Plus`|指示此 PE 文件在 64 位平台上运行。|  
|`pe32Unmanaged`|指示此 PE 文件是本机代码。|  
|pe32BitPreferred|指示此 PE 文件与平台无关，并且更适合于创建要在 32 位环境中加载。|  
  
## <a name="remarks"></a>备注  
 按位组合中，可以使用这些值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [元数据枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
