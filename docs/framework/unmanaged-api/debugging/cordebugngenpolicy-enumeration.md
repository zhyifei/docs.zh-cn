---
title: "CorDebugNGenPolicy 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugNGenPolicy
helpviewer_keywords: CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6042d5232995e68a4f59dfa68093446a03badfd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugngenpolicy-enumeration"></a>CorDebugNGenPolicy 枚举
提供用于确定调试器是否从本机映像缓存中加载本机 (NGen) 映像的值。  
  
## <a name="syntax"></a>语法  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a>成员  
  
|成员名称|描述|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|在[!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)]禁用应用程序中，使用从本地本机映像缓存的图像。 在桌面应用中，此设置不起。|  
  
## <a name="remarks"></a>备注  
 `CorDebugNGENPolicy`枚举由[icordebugprocess5:: Enablengenpolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)方法。 禁用的本地本机映像缓存中的映像使用通过确保调试器加载可调试 JIT 编译的映像，而不是优化的本机映像提供一致的调试体验。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
