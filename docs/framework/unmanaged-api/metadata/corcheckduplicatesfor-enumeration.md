---
title: CorCheckDuplicatesFor 枚举
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 6b551743227dc1c6069796038782a515e6dbe8c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443788"
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor 枚举
指定将检查重复项的元数据标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =   
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |   
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`MDDupAll`|检查所有元数据标记的重复项。|  
|`MDDupENC`|未使用。|  
|`MDNoDupChecks`|请勿检查重复项的元数据标记。|  
|`MDDupTypeDef`|检查 `mdTypeDef` 标记的重复项。|  
|`MDDupInterfaceImpl`|检查 `mdInterfaceImpl` 标记的重复项。|  
|`MDDupMethodDef`|检查 `mdMethodDef` 标记的重复项。|  
|`MDDupTypeRef`|检查 `mdTypeRef` 标记的重复项。|  
|`MDDupMemberRef`|检查 `mdMemberRef` 标记的重复项。|  
|`MDDupCustomAttribute`|检查 `mdCustomAttribute` 标记的重复项。|  
|`MDDupParamDef`|检查 `mdParamDef` 标记的重复项。|  
|`MDDupPermission`|检查 `mdPermission` 标记的重复项。|  
|`MDDupProperty`|检查 `mdProperty` 标记的重复项。|  
|`MDDupEvent`|检查 `mdEvent` 标记的重复项。|  
|`MDDupFieldDef`|检查 `mdFieldDef` 标记的重复项。|  
|`MDDupSignature`|检查 `mdSignature` 标记的重复项。|  
|`MDDupModuleRef`|检查 `mdModuleRef` 标记的重复项。|  
|`MDDupTypeSpec`|检查 `mdTypeSpec` 标记的重复项。|  
|`MDDupImplMap`|检查 `mdImplMap` 标记的重复项。|  
|`MDDupAssemblyRef`|检查 `mdAssemblyRef` 标记的重复项。|  
|`MDDupFile`|检查 `mdFile` 标记的重复项。|  
|`MDDupExportedType`|检查 `mdExportedType` 标记的重复项。|  
|`MDDupManifestResource`|检查 `mdManifestResource` 标记的重复项。|  
|`MDDupGenericParam`|检查 `mdGenericParam` 标记的重复项。|  
|`MDDupMethodSpec`|检查 `mdMethodSpec` 标记的重复项。|  
|`MDDupGenericParamConstraint`|检查 `mdGenericParamConstraint` 标记的重复项。|  
|`MDDupAssembly`|检查 `mdAssembly` 标记的重复项。|  
|`MDDupDefault`|检查 `mdMemberRef`、`mdTypeRef`、`mdSignature`、`mdTypeSpec`和 `mdMethodSpec` 标记的重复项。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corhdr。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
