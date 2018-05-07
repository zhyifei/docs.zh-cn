---
title: RUNTIME_INFO_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e544db23abf89a20bd2f7763cfdb1256ea4a326c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="runtimeinfoflags-enumeration"></a>RUNTIME_INFO_FLAGS 枚举
包含值，用于指示应返回有关公共语言运行时 (CLR) 的哪些信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|指示不应包含目录信息。|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|指示不应包含版本信息。|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|指示应在失败时显示错误对话框。|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|指示调用的效果[SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) SEM_FAILCRITICALERRORS 标志的函数应重写。 即一个安装对话框应显示在失败，而不是禁止显示时。|  
|`RUNTIME_INFO_REQUEST_AMD64`|指示 AMD 64 兼容版本的运行时信息的请求。|  
|`RUNTIME_INFO_REQUEST_IA64`|指示运行时的 IA 64 兼容版本有关的信息的请求。|  
|`RUNTIME_INFO_REQUEST_X86`|指示 x86 兼容版本的运行时信息的请求。|  
|`RUNTIME_INFO_UPGRADE_VERSION`|指示应包括版本升级的信息。|  
  
## <a name="remarks"></a>备注  
 以下的平台体系结构标志可以是一次只能指定的一个，并且不能结合使用：  
  
-   RUNTIME_INFO_REQUEST_IA64  
  
-   RUNTIME_INFO_REQUEST_AMD64  
  
-   RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
