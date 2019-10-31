---
title: ICorDebugNativeFrame 接口
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: 04bdbc49217236bc6c05a718cb4d42067cafd8bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096678"
---
# <a name="icordebugnativeframe-interface"></a>ICorDebugNativeFrame 接口

用于本机帧的 ICorDebugFrame 的专用实现。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CanSetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|获取一个值，该值指示是否可以安全地将指令指针设置为本机代码中的指定偏移位置。|  
|[GetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|获取堆栈帧到本机代码的偏移量。|  
|[GetLocalDoubleRegisterValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|获取一个指向 ICorDebugValue 的指针，该指针表示存储在本机帧的两个内存寄存器中的参数或局部变量的值。|  
|[GetLocalMemoryRegisterValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|获取一个指向 `ICorDebugValue` 的指针，该指针表示本地变量的值，其中低位存储在指定的寄存器中，高位存储在指定的内存地址。|  
|[GetLocalMemoryValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|获取一个指向 `ICorDebugValue` 的指针，该指针表示存储在指定内存地址中的局部变量的值。|  
|[GetLocalRegisterMemoryValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|获取一个指向 `ICorDebugValue` 的指针，该指针表示本地变量的值，其中高位存储在指定的寄存器中，低位存储在指定的内存地址|  
|[GetLocalRegisterValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|获取一个指向 `ICorDebugValue` 的指针，该指针表示存储在指定本机寄存器中的参数值或本地变量的值。|  
|[GetRegisterSet 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|获取一个指向[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)的指针，该指针表示此 `ICorDebugNativeFrame`的注册集。|  
|[SetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|将指令指针设置为本机代码中的指定偏移位置。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
