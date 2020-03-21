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
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176183"
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor 枚举
指定将检查重复项的元数据令牌。  
  
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
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`MDDupAll`|检查所有元数据令牌的重复项。|  
|`MDDupENC`|未使用。|  
|`MDNoDupChecks`|不要检查元数据令牌的重复项。|  
|`MDDupTypeDef`|检查令牌的`mdTypeDef`重复项。|  
|`MDDupInterfaceImpl`|检查令牌的`mdInterfaceImpl`重复项。|  
|`MDDupMethodDef`|检查令牌的`mdMethodDef`重复项。|  
|`MDDupTypeRef`|检查令牌的`mdTypeRef`重复项。|  
|`MDDupMemberRef`|检查令牌的`mdMemberRef`重复项。|  
|`MDDupCustomAttribute`|检查令牌的`mdCustomAttribute`重复项。|  
|`MDDupParamDef`|检查令牌的`mdParamDef`重复项。|  
|`MDDupPermission`|检查令牌的`mdPermission`重复项。|  
|`MDDupProperty`|检查令牌的`mdProperty`重复项。|  
|`MDDupEvent`|检查令牌的`mdEvent`重复项。|  
|`MDDupFieldDef`|检查令牌的`mdFieldDef`重复项。|  
|`MDDupSignature`|检查令牌的`mdSignature`重复项。|  
|`MDDupModuleRef`|检查令牌的`mdModuleRef`重复项。|  
|`MDDupTypeSpec`|检查令牌的`mdTypeSpec`重复项。|  
|`MDDupImplMap`|检查令牌的`mdImplMap`重复项。|  
|`MDDupAssemblyRef`|检查令牌的`mdAssemblyRef`重复项。|  
|`MDDupFile`|检查令牌的`mdFile`重复项。|  
|`MDDupExportedType`|检查令牌的`mdExportedType`重复项。|  
|`MDDupManifestResource`|检查令牌的`mdManifestResource`重复项。|  
|`MDDupGenericParam`|检查令牌的`mdGenericParam`重复项。|  
|`MDDupMethodSpec`|检查令牌的`mdMethodSpec`重复项。|  
|`MDDupGenericParamConstraint`|检查令牌的`mdGenericParamConstraint`重复项。|  
|`MDDupAssembly`|检查令牌的`mdAssembly`重复项。|  
|`MDDupDefault`|检查`mdMemberRef`、、、`mdTypeRef``mdSignature``mdTypeSpec`和`mdMethodSpec`令牌的重复项。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫德  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
