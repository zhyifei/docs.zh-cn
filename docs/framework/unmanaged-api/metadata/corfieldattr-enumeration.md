---
title: CorFieldAttr 枚举
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a57318103fd875d6f2f2fe4ca54c776da86c0e53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="corfieldattr-enumeration"></a>CorFieldAttr 枚举
包含一些值，用于描述字段的相应元数据。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`fdFieldAccessMask`|指定的辅助功能信息。|  
|`fdPrivateScope`|指定不能引用字段。|  
|`fdPrivate`|指定字段为只能由其父类型访问。|  
|`fdFamANDAssem`|指定该字段是由在其程序集的派生类可访问。|  
|`fdAssembly`|指定字段为可通过在程序集中的所有类型访问。|  
|`fdFamily`|指定字段为只能由其类型访问，并且派生类。|  
|`fdFamORAssem`|指定字段为可由派生类和在程序集中的所有类型访问。|  
|`fdPublic`|指定字段具有可见性的所有类型，此范围的可访问。|  
|`fdStatic`|指定字段为其类型的成员而不是实例成员。|  
|`fdInitOnly`|指定该字段进行初始化之后无法更改。|  
|`fdLiteral`|指定的字段值是编译时常量。|  
|`fdNotSerialized`|指定项目其类型为进行远程处理时，该字段不会序列化。|  
|`fdSpecialName`|指定字段为特殊，其名称描述如何。|  
|`fdPinvokeImpl`|指定的字段实现通过 PInvoke 转发。|  
|`fdReservedMask`|保留供内部使用公共语言运行时。|  
|`fdRTSpecialName`|指定公共语言运行时元数据内部 Api 应检查该名称的编码。|  
|`fdHasFieldMarshal`|指定该字段包含封送处理信息。|  
|`fdHasDefault`|指定字段具有默认值。|  
|`fdHasFieldRVA`|指定字段具有的相对虚拟地址。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
