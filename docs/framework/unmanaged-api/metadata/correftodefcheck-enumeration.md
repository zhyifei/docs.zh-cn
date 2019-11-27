---
title: CorRefToDefCheck 枚举
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: e6c3c9b842bd823e8975661964480fd801779b2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450130"
---
# <a name="correftodefcheck-enumeration"></a>CorRefToDefCheck 枚举
指定用于控制将哪些引用项转换为相应定义以优化代码的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`MDRefToDefDefault`|指定应将类型引用和成员引用转换为定义。 这是默认值（`MDTypeRefToDef` &#124; `MDMemberRefToDef`）。|  
|`MDRefToDefAll`|指定所有引用项都应转换为定义。|  
|`MDRefToDefNone`|指定不应将引用项转换为定义。|  
|`MDTypeRefToDef`|指定仅类型引用应转换为类型定义。|  
|`MDMemberRefToDef`|指定只应将成员引用转换为定义。 也就是说，应将成员引用转换为方法定义或字段定义。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corhdr。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
