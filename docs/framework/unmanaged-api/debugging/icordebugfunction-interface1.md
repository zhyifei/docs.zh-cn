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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae65c59efe1d925b5e058e8664d1e093fdfec875
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917208"
---
# <a name="icordebugfunction-interface"></a>ICorDebugFunction 接口

表示一个托管函数或方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateBreakpoint 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|在此函数的开头创建一个断点。|  
|[GetClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|获取一个 ICorDebugClass 对象, 该对象表示此函数所属的类。|  
|[GetCurrentVersionNumber 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|获取对此函数进行的最新编辑的版本号。|  
|[GetILCode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|获取此函数的 Microsoft 中间语言 (MSIL) 代码。|  
|[GetLocalVarSigToken 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|获取由此`ICorDebugFunction`实例表示的函数的局部变量签名的元数据标记。|  
|[GetModule 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|获取在其中定义此函数的模块。|  
|[GetNativeCode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|获取此函数的本机代码。|  
|[GetToken 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|获取此函数的元数据标记。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugFunction`接口不表示包含泛型类型参数的函数。 例如, 一个实例`ICorDebugFunction`将表示`Func<T>` , 而不`Func<string>`是。 调用[ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)以获取泛型类型参数。  
  
 方法的元数据标记、 `mdMethodDef`和方法的`ICorDebugFunction`对象之间的关系取决于函数是否允许 "编辑并继续":  
  
- 如果函数上不允许使用 "编辑并继续", 则在`ICorDebugFunction`对象`mdMethodDef`与标记之间存在一对一关系。 也就是说, 该函数有一个`ICorDebugFunction`对象和一个`mdMethodDef`标记。  
  
- 如果允许在函数上使用 "编辑并继续", 则在`ICorDebugFunction`对象`mdMethodDef`与标记之间存在多对一关系。 也就是说, 该函数可能有多个实例`ICorDebugFunction`, 每个版本一个, 而只是一个`mdMethodDef`标记。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
