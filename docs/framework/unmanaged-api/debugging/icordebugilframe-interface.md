---
title: ICorDebugILFrame 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a97704e00278e19181df569f108f428cb1ec90f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417740"
---
# <a name="icordebugilframe-interface1"></a>ICorDebugILFrame 接口 1
表示 Microsoft 中间语言 (MSIL) 代码的堆栈帧。 此接口是 ICorDebugFrame 接口的子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CanSetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|获取一个值，该值指示是否可以安全地将指令指针设置为指定的偏移位置。|  
|[EnumerateArguments 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|此帧中获取自变量的枚举数。|  
|[EnumerateLocalVariables 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|此帧中获取的本地变量的枚举数。|  
|[GetArgument 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|获取此 MSIL 堆栈帧中指定的自变量的值。|  
|[GetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|获取指令指针的值和一个描述如何获取指令指针的值的按位组合值。|  
|[GetLocalVariable 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|获取此 MSIL 堆栈帧中指定的本地变量的值。|  
|[GetStackDepth 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|未实现。|  
|[GetStackValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|未实现。|  
|[SetIP 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|将指令指针设置为 MSIL 代码中的指定偏移位置。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugILFrame`接口是专用的 ICorDebugFrame 接口。 使用它为 MSIL 代码帧或实时 (JIT) 编译的帧。 JIT 编译帧实现`ICorDebugILFrame`接口和 ICorDebugNativeFrame 接口。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
