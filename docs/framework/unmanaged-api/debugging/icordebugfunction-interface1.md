---
title: ICorDebugFunction 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
ms.openlocfilehash: ba0e0b1b2bac785e28f41e09dda74841121a748d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794504"
---
# <a name="icordebugfunction-interface"></a>ICorDebugFunction 接口

表示一个托管函数或方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateBreakpoint 方法](icordebugfunction-createbreakpoint-method.md)|在此函数的开头创建一个断点。|  
|[GetClass 方法](icordebugfunction-getclass-method.md)|获取一个 ICorDebugClass 对象，该对象表示此函数所属的类。|  
|[GetCurrentVersionNumber 方法](icordebugfunction-getcurrentversionnumber-method.md)|获取对此函数进行的最新编辑的版本号。|  
|[GetILCode 方法](icordebugfunction-getilcode-method.md)|获取此函数的 Microsoft 中间语言（MSIL）代码。|  
|[GetLocalVarSigToken 方法](icordebugfunction-getlocalvarsigtoken-method.md)|获取此 `ICorDebugFunction` 实例所表示的函数的局部变量签名的元数据标记。|  
|[GetModule 方法](icordebugfunction-getmodule-method.md)|获取在其中定义此函数的模块。|  
|[GetNativeCode 方法](icordebugfunction-getnativecode-method.md)|获取此函数的本机代码。|  
|[GetToken 方法](icordebugfunction-gettoken-method.md)|获取此函数的元数据标记。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugFunction` 接口不表示包含泛型类型参数的函数。 例如，`ICorDebugFunction` 实例将表示 `Func<T>` 而不是 `Func<string>`。 调用[ICorDebugILFrame2：： EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md)以获取泛型类型参数。  
  
 方法的元数据标记、`mdMethodDef`和方法 `ICorDebugFunction` 对象之间的关系取决于函数是否允许 "编辑并继续"：  
  
- 如果函数上不允许使用 "编辑并继续"，则 `ICorDebugFunction` 对象与 `mdMethodDef` 标记之间存在一对一关系。 也就是说，该函数有一个 `ICorDebugFunction` 对象和一个 `mdMethodDef` 标记。  
  
- 如果允许在函数上使用 "编辑并继续"，则 `ICorDebugFunction` 对象与 `mdMethodDef` 标记之间存在多对一的关系。 也就是说，该函数可能有多个 `ICorDebugFunction`实例，每个版本对应一个函数，但只有一个 `mdMethodDef` 标记。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** Corguids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
