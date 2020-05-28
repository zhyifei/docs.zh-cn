---
title: CorSaveSize 枚举
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
ms.openlocfilehash: 22a7f87a5803dc185052a5ce7ed427eff9f8fb18
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009179"
---
# <a name="corsavesize-enumeration"></a>CorSaveSize 枚举
包含一些值，用于指示查询保存操作的大小时所需的精度级别。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`cssAccurate`|指定返回值应是精确的。|  
|`cssQuick`|指定应估算返回值。|  
|`cssDiscardTransientCAs`|指定应删除可放弃类型。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Corhdr。h  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据枚举](metadata-enumerations.md)
