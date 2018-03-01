---
title: "ESymbolReadingPolicy 枚举"
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
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fdb18a343f91e85619f6d62e466fdd558044727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="esymbolreadingpolicy-enumeration"></a>ESymbolReadingPolicy 枚举
包含将读取程序数据库 (PDB) 文件的策略设置的值。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`eSymbolReadingAlways`|指定调试器应始终阅读 PDB 文件。|  
|`eSymbolReadingFullTrustOnly`|指定调试器应读取与完全信任程序集关联的 PDB 文件。|  
|`eSymbolReadingNever`|指定调试器应永远不会读取 PDB 文件。|  
  
## <a name="remarks"></a>备注  
 `ESymbolReadingPolicy`枚举用于[iclrdebugmanager:: Setsymbolreadingpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
