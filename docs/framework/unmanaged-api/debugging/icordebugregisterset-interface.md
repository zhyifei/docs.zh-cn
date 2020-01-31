---
title: ICorDebugRegisterSet 接口
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: f435db28d5c85d576f69e7612841fc46ae142332
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792071"
---
# <a name="icordebugregisterset-interface"></a>ICorDebugRegisterSet 接口
表示在当前正在执行代码的计算机上可用的寄存器集。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetRegisters 方法](icordebugregisterset-getregisters-method.md)|获取位掩码指定的每个寄存器的值（在当前正在执行代码的计算机上）。|  
|[GetRegistersAvailable 方法](icordebugregisterset-getregistersavailable-method.md)|获取一个位掩码，指示此 `ICorDebugRegisterSet` 中的哪些寄存器当前可用。|  
|[GetThreadContext 方法](icordebugregisterset-getthreadcontext-method.md)|获取当前线程的上下文。|  
|[SetRegisters 方法](icordebugregisterset-setregisters-method.md)|未实现 .NET Framework 版本2.0。|  
|[SetThreadContext 方法](icordebugregisterset-setthreadcontext-method.md)|未实现 2.0 .NET Framework。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugRegisterSet` 接口仅支持32位寄存器。 使用需要额外注册的平台（如 IA-64）上的[ICorDebugRegisterSet2](icordebugregisterset2-interface.md)接口。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [ICorDebugRegisterSet2 接口](icordebugregisterset2-interface.md)
