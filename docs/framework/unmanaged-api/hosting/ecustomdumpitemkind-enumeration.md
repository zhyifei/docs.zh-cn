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
ms.openlocfilehash: 12a1142759532890f541a7c81006f8b3aed4d299
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616263"
---
# <a name="ecustomdumpitemkind-enumeration"></a>ECustomDumpItemKind 枚举
保留以供将来扩展[CustomDumpItem](customdumpitem-structure.md)结构。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    DUMP_ITEM_None = 0  
} ECustomDumpItemKind;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`DUMP_ITEM_None`|保留供将来使用。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRErrorReportingManager 接口](iclrerrorreportingmanager-interface.md)
- [承载枚举](hosting-enumerations.md)
