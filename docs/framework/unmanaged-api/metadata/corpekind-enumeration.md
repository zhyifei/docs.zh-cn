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
ms.openlocfilehash: 8b6eab8156f72847eb6dd3369950f9b46a3fc877
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007554"
---
# <a name="corpekind-enumeration"></a>CorPEKind 枚举
包含描述可移植可执行（PE）文件的值，这些值是从对[IMetaDataImport2：： GetPEKind](imetadataimport2-getpekind-method.md)的调用返回的。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
|`peILOnly`|指示此 PE 文件仅包含托管代码。|  
|`pe32BitRequired`|指示此 PE 文件进行 Win32 调用。|  
|`pe32Plus`|指示此 PE 文件在64位平台上运行。|  
|`pe32Unmanaged`|指示此 PE 文件是本机代码。|  
|pe32BitPreferred|指示此 PE 文件与平台无关，并倾向于在32位环境中加载。|  
  
## <a name="remarks"></a>备注  
 这些值可用于按位组合。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Corhdr。h  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据枚举](metadata-enumerations.md)
