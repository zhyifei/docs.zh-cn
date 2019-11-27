---
title: CorTokenType 枚举
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
ms.openlocfilehash: 74807a678b5c0c2738f33fe552f6462af93ca1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436463"
---
# <a name="cortokentype-enumeration"></a>CorTokenType 枚举
指示元数据标记的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`mdtModule`|`mdModule` 标记。|  
|`mdtTypeRef`|`mdTypeRef` 标记。|  
|`mdtTypeDef`|`mdTypeDef` 标记。|  
|`mdtFieldDef`|`mdFieldDef` 标记。|  
|`mdtMethodDef`|`mdMethodDef` 标记。|  
|`mdtParamDef`|`mdParamDef` 标记。|  
|`mdtInterfaceImpl`|`mdInterfaceImpl` 标记。|  
|`mdtMemberRef`|`mdMemberRef` 标记。|  
|`mdtCustomAttribute`|`mdCustomAttribute` 标记。|  
|`mdtPermission`|`mdPermission` 标记。|  
|`mdtSignature`|`mdSignature` 标记。|  
|`mdtEvent`|`mdEvent` 标记。|  
|`mdtProperty`|`mdProperty` 标记。|  
|`mdtModuleRef`|`mdModuleRef` 标记。|  
|`mdtTypeSpec`|`mdTypeSpec` 标记。|  
|`mdtAssembly`|`mdAssembly` 标记。|  
|`mdtAssemblyRef`|`mdAssemblyRef` 标记。|  
|`mdtFile`|`mdFile` 标记。|  
|`mdtExportedType`|`mdExportedType` 标记。|  
|`mdtManifestResource`|`mdManifestResource` 标记。|  
|`mdtGenericParam`|`mdGenericParam` 标记。|  
|`mdtMethodSpec`|`mdMethodSpec` 标记。|  
|`mdtGenericParamConstraint`|`mdGenericParamConstraint` 标记。|  
|`mdtString`|`mdString` 标记。|  
|`mdtName`|`mdName` 标记。|  
|`mdtBaseType`|未使用。|  
  
## <a name="remarks"></a>备注  
 每个值都等于对应的元数据标记中的顶部字节的值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corhdr。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
