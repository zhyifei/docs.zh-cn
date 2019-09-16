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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c01346b42fff812f8358482ae0e8570c03ee9231
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912798"
---
# <a name="icordebugnativeframe-interface"></a>ICorDebugNativeFrame 接口

用于本机帧的 ICorDebugFrame 的专用实现。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CanSetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|获取一个值，该值指示是否可以安全地将指令指针设置为本机代码中的指定偏移位置。|  
|[GetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|获取堆栈帧到本机代码的偏移量。|  
|[GetLocalDoubleRegisterValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|获取一个指向 ICorDebugValue 的指针，该指针表示存储在本机帧的两个内存寄存器中的参数或局部变量的值。|  
|[GetLocalMemoryRegisterValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|获取一个指向`ICorDebugValue`的指针，该指针表示本地变量的值，其中低位存储在指定的寄存器中，高位存储于指定的内存地址。|  
|[GetLocalMemoryValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|获取一个指向`ICorDebugValue`的指针，该指针表示存储在指定内存地址中的局部变量的值。|  
|[GetLocalRegisterMemoryValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|获取一个指向`ICorDebugValue`的指针，该指针表示本地变量的值，其中高位存储在指定的寄存器中，低位存储在指定的内存地址|  
|[GetLocalRegisterValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|获取一个指向`ICorDebugValue`的指针，该指针表示存储在指定本机寄存器中的参数或局部变量的值。|  
|[GetRegisterSet 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|获取一个指针，该指针指向表示此 `ICorDebugNativeFrame` 的注册集的 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)。|  
|[SetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|将指令指针设置为本机代码中的指定偏移位置。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl，Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
