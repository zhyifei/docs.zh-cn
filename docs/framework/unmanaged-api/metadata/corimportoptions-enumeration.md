---
title: CorImportOptions 枚举
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
ms.openlocfilehash: 44d1776e2902988353ef4fd58aca20e56203b9da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442842"
---
# <a name="corimportoptions-enumeration"></a>CorImportOptions 枚举
包含一些标志值，用于在导入当前作用域范围外的程序集的过程中控制行为。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`MDImportOptionDefault`|指示用于跳过已删除记录的默认行为。|  
|`MDImportOptionAll`|指示应枚举所有元数据。|  
|`MDImportOptionAllTypeDefs`|指示应枚举所有的 Typedef （包括删除的）。|  
|`MDImportOptionAllMethodDefs`|指示应枚举所有 MethodDefs （包括删除的）。|  
|`MDImportOptionAllFieldDefs`|指示应枚举所有 FieldDefs （包括删除的）。|  
|`MDImportOptionAllProperties`|指示应枚举所有 PropertyDefs （包括删除的）。|  
|`MDImportOptionAllEvents`|指示应枚举所有 EventDefs （包括删除的）。|  
|`MDImportOptionAllCustomAttributes`|指示应对所有自定义属性（包括删除的）进行枚举。|  
|`MDImportOptionAllExportedTypes`|指示应对所有导出的类型（包括已删除的）进行枚举。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corhdr。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
