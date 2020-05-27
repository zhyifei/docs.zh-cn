---
title: CorNotificationForTokenMovement 枚举
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: e8065a5492884a4b7f5d662737e4beddc6fca5b3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007593"
---
# <a name="cornotificationfortokenmovement-enumeration"></a>CorNotificationForTokenMovement 枚举
指定在进行标记重新映射时将发送到元数据 API 客户端的通知。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`MDNotifyDefault`|当 `mdTypeRef` 、、 `mdMethodDef` `mdMemberRef` 或 `mdFieldDef` 标记移动时通知。|  
|`MDNotifyAll`|任何标记移动时发出通知。|  
|`MDNotifyNone`|标记移动时不发出通知。|  
|`MDNotifyMethodDef`|移动令牌时发出通知 `mdMethodDef` 。|  
|`MDNotifyMemberRef`|移动令牌时发出通知 `mdMemberRef` 。|  
|`MDNotifyFieldDef`|移动令牌时发出通知 `mdFieldDef` 。|  
|`MDNotifyTypeRef`|移动令牌时发出通知 `mdTypeRef` 。|  
|`MDNotifyTypeDef`|移动令牌时发出通知 `mdTypeDef` 。|  
|`MDNotifyParamDef`|移动令牌时发出通知 `mdParamDef` 。|  
|`MDNotifyInterfaceImpl`|移动令牌时发出通知 `mdInterfaceImpl` 。|  
|`MDNotifyProperty`|移动令牌时发出通知 `mdProperty` 。|  
|`MDNotifyEvent`|移动令牌时发出通知 `mdEvent` 。|  
|`MDNotifySignature`|移动令牌时发出通知 `mdSignature` 。|  
|`MDNotifyTypeSpec`|移动令牌时发出通知 `mdTypeSpec` 。|  
|`MDNotifyCustomAttribute`|移动令牌时发出通知 `mdCustomAttribute` 。|  
|`MDNotifySecurityValue`|移动令牌时发出通知 `mdSecurityValue` 。|  
|`MDNotifyPermission`|移动令牌时发出通知 `mdPermission` 。|  
|`MDNotifyModuleRef`|移动令牌时发出通知 `mdModuleRef` 。|  
|`MDNotifyNameSpace`|移动令牌时发出通知 `mdNameSpace` 。|  
|`MDNotifyAssemblyRef`|移动令牌时发出通知 `mdAssemblyRef` 。|  
|`MDNotifyFile`|移动令牌时发出通知 `mdFile` 。|  
|`MDNotifyExportedType`|移动令牌时发出通知 `mdExportedType` 。|  
|`MDNotifyResource`|移动令牌时发出通知 `mdManifestResource` 。|  
  
## <a name="remarks"></a>备注  
 可在元数据合并期间重新映射（即，移动）标记。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Corhdr。h  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据枚举](metadata-enumerations.md)
