---
title: "CorDebugGCType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugGCType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGCType
helpviewer_keywords: CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 14d6f28c2e5fa356c7f406ffb4c2787f0ace500a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuggctype-enumeration"></a>CorDebugGCType 枚举
指示垃圾回收器是在工作站还是服务器上运行。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a>参数  
  
## <a name="members"></a>成员  
  
|成员名称|描述|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|在工作站上运行垃圾回收器。|  
|`CorDebugServerGC`|在服务器上运行垃圾回收器。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
