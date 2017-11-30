---
title: "CorDebugSetContextFlag 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugSetContextFlag
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugSetContextFlag
helpviewer_keywords: CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 958ed303fab3dcb01fad2040dd06381e76fe5a00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugsetcontextflag-enumeration"></a>CorDebugSetContextFlag 枚举
指示上下文是来自堆栈上的活动（或叶）帧，还是已通过从另一个帧展开来进行计算。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|SET_CONTEXT_FLAG_ACTIVE_FRAME|上下文是线程的活动上下文。|  
|SET_CONTEXT_FLAG_UNWIND_FRAME|已通过从另一个帧展开来计算上下文。|  
  
## <a name="remarks"></a>备注  
 `CorDebugSetContextFlag`提供使用的值[icordebugstackwalk:: Setcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)方法。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
