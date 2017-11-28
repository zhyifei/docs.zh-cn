---
title: "ICorDebugValue2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue2
helpviewer_keywords: ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f74a90952c6ac780c53441af472faeb999febbb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue2-interface"></a>ICorDebugValue2 接口
扩展"ICorDebugValue"接口，若要为"ICorDebugType"对象提供支持。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetExactType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|获取到的接口指针`ICorDebugType`对象，表示<xref:System.Type>的此值。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
    
 [ICorDebugValue3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
