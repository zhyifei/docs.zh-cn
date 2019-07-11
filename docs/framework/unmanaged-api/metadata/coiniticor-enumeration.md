---
title: COINITICOR 枚举
ms.date: 03/30/2017
api_name:
- COINITICOR
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITICOR
helpviewer_keywords:
- COINITICOR enumeration [.NET Framework metadata]
ms.assetid: 67fefd89-28d6-4588-84ea-dc7a5870e014
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89d2f9c9cfa7d4c2498710b36796f3e2605bcbf0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763648"
---
# <a name="coiniticor-enumeration"></a>COINITICOR 枚举
指定使用的常量[CoInitializeCor](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)当它初始化公共语言运行时。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum tagCOINITCOR  
{  
    COINITCOR = 0x0  
} COINITICOR;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`COINITCOR`|指示默认初始化模式。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 包含为 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
