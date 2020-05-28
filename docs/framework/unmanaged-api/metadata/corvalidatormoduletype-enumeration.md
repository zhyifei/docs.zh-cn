---
title: CorValidatorModuleType 枚举
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
ms.openlocfilehash: 038e2ec20e5fd01edf9835080e0f7a15ec862fd9
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008932"
---
# <a name="corvalidatormoduletype-enumeration"></a>CorValidatorModuleType 枚举
指定模块的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|模块是无效类型。|  
|`ValidatorModuleTypeMin`|枚举的最小值 `CorValidatorModuleType` 。|  
|`ValidatorModuleTypePE`|模块是可移植可执行（PE）文件。|  
|`ValidatorModuleTypeObj`|模块是 .obj 文件。|  
|`ValidatorModuleTypeEnc`|模块是 "编辑并继续" 调试器会话。|  
|`ValidatorModuleTypeIncr`|模块是增量生成的模块。|  
|`ValidatorModuleTypeMax`|枚举的最大值 `CorValidatorModuleType` 。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据枚举](metadata-enumerations.md)
