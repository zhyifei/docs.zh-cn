---
title: "ICorDebugVirtualUnwinder 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d22fa926b300384b7f790468b1b3d0becafdb942
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvirtualunwinder-interface"></a>ICorDebugVirtualUnwinder 接口
提供帮助堆栈展开的方法。  
  
## <a name="methods"></a>方法  
  
|方法|名称|  
|------------|----------|  
|[GetContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|获取此展开器的当前上下文。|  
|[Next 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|前进到调用方的上下文。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugVirtualUnwinder` 接口的成员由调试器来实现，从而在堆栈展开中提供帮助。  
  
> [!NOTE]
>  此接口仅适用于 .NET Native。 如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
