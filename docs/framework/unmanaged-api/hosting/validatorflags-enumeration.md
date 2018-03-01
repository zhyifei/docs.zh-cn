---
title: "ValidatorFlags 枚举"
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
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 952944e9ae9a8186a182796deb587b6fa6a0d6a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="validatorflags-enumeration"></a>ValidatorFlags 枚举
包含值，用于指示应在调用中执行的验证的类型[iclrvalidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|指定应验证的仅 Microsoft 中间语言 (MSIL) 中的可执行文件。|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|指定应验证仅可执行文件的格式。|  
|`VALIDATOR_EXTRA_VERBOSE`|指定应执行和报告所有类型的验证。|  
|`VALIDATOR_NOCHECK_PEFORMAT`|指定不应验证可执行文件的格式。|  
|`VALIDATOR_SHOW_SOURCE_LINES`|指定验证错误消息应包括引发验证错误的源代码行。 .NET Framework 2.0 版中，此字段值无效。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** IValidator.idl、 IValidator.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRErrorReportingManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
