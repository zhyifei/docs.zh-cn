---
title: "CorMethodAttr 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4e144b64664a149115f3047b98267c2f218a76e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodattr-enumeration"></a>CorMethodAttr 枚举
包含值，用于描述方法的功能。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`mdMemberAccessMask`|指定成员访问。|  
|`mdPrivateScope`|指定该成员不能被引用。|  
|`mdPrivate`|指定的成员是只能由父类型访问。|  
|`mdFamANDAssem`|指定的成员是可访问的子类型仅在此程序集。|  
|`mdAssem`|指定的成员是可在程序集中的任何人。|  
|`mdFamily`|指定的成员是只能由类型和子类型访问。|  
|`mdFamORAssem`|指定的成员是可由派生类和在其程序集的其他类型访问。|  
|`mdPublic`|指定成员可由具有访问权限的所有类型到的作用域访问。|  
|`mdStatic`|指定该成员已定义类型的一部分，而不是实例的成员。|  
|`mdFinal`|指定不重写方法。|  
|`mdVirtual`|指定该方法可以重写。|  
|`mdHideBySig`|指定的方法隐藏按名称和签名，而不是只按名称。|  
|`mdVtableLayoutMask`|指定虚拟表布局。|  
|`mdReuseSlot`|指定用于虚拟表中的此方法的槽可重复使用。 这是默认设置。|  
|`mdNewSlot`|指定该方法总是获取虚拟表中的新槽。|  
|`mdCheckAccessOnOverride`|指定可以对其是可见的相同类型中重写该方法。|  
|`mdAbstract`|指定未实现方法。|  
|`mdSpecialName`|指定该方法是特殊的并且其名称描述如何。|  
|`mdPinvokeImpl`|指定使用 PInvoke 转发方法的实现。|  
|`mdUnmanagedExport`|指定的方法是导出到非托管代码的托管的方法。|  
|`mdReservedMask`|保留供内部使用公共语言运行时。|  
|`mdRTSpecialName`|指定公共语言运行时，应检查的方法名称的编码。|  
|`mdHasSecurity`|指定该方法有与之关联的安全。|  
|`mdRequireSecObject`|指定该方法调用包含安全代码的另一种方法。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
