---
title: "CorDebugMappingResult 枚举"
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
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 924cfec87b99cba9621af02d4e78e72094060ae8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugmappingresult-enumeration"></a>CorDebugMappingResult 枚举
提供如何获取指令指针 (IP) 的值的详细信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`MAPPING_PROLOG`|本机代码是在序言中，因此 IP 的值为 0。|  
|`MAPPING_EPILOG`|本机代码处于 epilog，所以 IP 的值是该方法的最后一个指令的地址。|  
|`MAPPING_NO_INFO`|没有映射信息是可用的方法，因此 IP 的值为 0。|  
|`MAPPING_UNMAPPED_ADDRESS`|尽管没有映射信息的方法，但当前的地址不能映射到 Microsoft 中间语言 (MSIL) 代码。 IP 的值为 0。|  
|`MAPPING_EXACT`|该方法准确地映射到 MSIL 代码，或者已解释了帧，因此 IP 的值为精确值。|  
|`MAPPING_APPROXIMATE`|已成功映射方法，但 IP 的值可能为近似值。|  
  
## <a name="remarks"></a>备注  
 你可以使用[icordebugilframe:: Getip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)方法来获取指令指针的值。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
