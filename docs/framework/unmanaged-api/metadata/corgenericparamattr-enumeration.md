---
title: CorGenericParamAttr 枚举
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176170"
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr 枚举
包含描述泛型类型的<xref:System.Type>参数的值，如调用[IMetaDataEmit2：:DefinegenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)中使用的。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`gpVarianceMask`|参数方差仅适用于接口和委托的泛型参数。|  
|`gpNonVariant`|指示不存在方差。|  
|`gpCovariant`|表示协方差。|  
|`gpContravariant`|表示不差异。|  
|`gpSpecialConstraintMask`|特殊约束可以应用于任何<xref:System.Type>参数。|  
|`gpNoSpecialConstraint`|指示没有约束应用于参数<xref:System.Type>。|  
|`gpReferenceTypeConstraint`|指示参数<xref:System.Type>必须是引用类型。|  
|`gpNotNullableValueTypeConstraint`|指示参数<xref:System.Type>必须是不能为空值的值类型。|  
|`gpDefaultConstructorConstraint`|指示<xref:System.Type>参数必须具有不需要参数的默认公共构造函数。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫德  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
