---
title: ECustomDumpItemKind 枚举
ms.date: 03/30/2017
api_name:
- ECustomDumpItemKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpItemKind
helpviewer_keywords:
- ECustomDumpItemKind enumeration [.NET Framework hosting]
ms.assetid: 7105a6c8-6e4e-48de-ac3d-74ac75e5de2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95b4e1762e5f7701bfce2edc4f7bd4f8cecb28b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747407"
---
# <a name="ecustomdumpitemkind-enumeration"></a>ECustomDumpItemKind 枚举
保留供将来的扩展[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)结构。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    DUMP_ITEM_None = 0  
} ECustomDumpItemKind;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`DUMP_ITEM_None`|留待将来使用。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRErrorReportingManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
