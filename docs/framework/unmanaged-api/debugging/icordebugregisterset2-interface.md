---
title: ICorDebugRegisterSet2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: 161358fab9a4601e7b718321273d493bd84a3228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792015"
---
# <a name="icordebugregisterset2-interface"></a>ICorDebugRegisterSet2 接口
为包含64个以上注册的硬件平台扩展了[ICorDebugRegisterSet](icordebugregisterset-interface.md)接口的功能。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetRegisters 方法](icordebugregisterset2-getregisters-method.md)|获取位掩码指定的每个寄存器的值（在当前正在执行代码的计算机上）。|  
|[GetRegistersAvailable 方法](icordebugregisterset2-getregistersavailable-method.md)|获取提供可用寄存器的位图的字节数组。|  
|[SetRegisters 方法](icordebugregisterset2-setregisters-method.md)|在 .NET Framework 版本2.0 中未实现。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [ICorDebugRegisterSet 接口](icordebugregisterset-interface.md)
