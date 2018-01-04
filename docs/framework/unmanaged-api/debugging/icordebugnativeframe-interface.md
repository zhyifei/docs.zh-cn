---
title: "ICorDebugNativeFrame 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame
helpviewer_keywords: ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edd49d745be9db0c4c5309cf5febc3ff651a860f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe-interface1"></a>ICorDebugNativeFrame 接口 1
ICorDebugFrame 用于本机帧的专用的实现。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CanSetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|获取一个值，该值指示是否可以安全地将指令指针设置为指定的偏移量位置，本机代码中。|  
|[GetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|获取到本机代码的堆栈帧的偏移量。|  
|[GetLocalDoubleRegisterValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|获取一个指针指向 ICorDebugValue 表示自变量或存储在两个内存寄存器中的本机框架的本地变量的值。|  
|[GetLocalMemoryRegisterValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|获取一个指向`ICorDebugValue`，表示本地变量，其中的低位存储在指定的寄存器，高位存储在指定的内存地址的值。|  
|[GetLocalMemoryValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|获取一个指向`ICorDebugValue`，表示存储在指定的内存地址的本地变量的值。|  
|[GetLocalRegisterMemoryValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|获取一个指向`ICorDebugValue`，表示本地变量，其中的高位存储在指定的寄存器，存储在指定的内存地址的低位的值|  
|[GetLocalRegisterValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|获取一个指向`ICorDebugValue`，表示的自变量或局部变量存储在指定的本机寄存器的值。|  
|[GetRegisterSet 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|获取一个指向[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)表示为此参数设置的寄存器`ICorDebugNativeFrame`。|  
|[SetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|将指令指针设置为指定的偏移量位置，在本机代码中。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
