---
title: "COR_TYPEID 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPEID
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPEID
helpviewer_keywords: COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 795dea77ac8dac1e1d22574c23f1e1c13344a71a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cortypeid-structure"></a>COR_TYPEID 结构
包含类型标识符。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`token1`|第一个标记。|  
|`token2`|第二个标记。|  
  
## <a name="remarks"></a>备注  
 `COR_TYPEID`结构返回由大量调试方法，提供有关要进行垃圾回收的对象的信息。 它可以然后作为参数传递给其他调试的方法，提供有关该项目的其他信息。 例如，通过枚举[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)对象，你可以检索各个[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)表示托管堆上的单个对象的对象。 然后可以将传递`COR_TYPEID`值从`COR_HEAPOBJECT.type`字段[icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)方法来检索一个 ICorDebugType 对象，提供有关对象的类型信息。  
  
 A`COR_TYPEID`对象用于不透明。 其各个字段不应访问或操作。 其唯一的用途是作为标识符用作`out`中参数的方法调用和可，反过来，传递给其他方法来提供其他信息。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
