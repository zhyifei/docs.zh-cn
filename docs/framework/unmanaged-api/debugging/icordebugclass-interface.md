---
title: ICorDebugClass 接口
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: 7ac588591222a1abbc7b99ec7e973284c055f95e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784169"
---
# <a name="icordebugclass-interface"></a>ICorDebugClass 接口

表示基类型或复杂类型（即用户定义的类型）。 如果该类型为泛型类型，则 `ICorDebugClass` 表示实例化的泛型类型。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetModule 方法](icordebugclass-getmodule-method.md)|获取定义此类的模块。|  
|[GetStaticFieldValue 方法](icordebugclass-getstaticfieldvalue-method.md)|获取指定的静态字段的值。|  
|[GetToken 方法](icordebugclass-gettoken-method.md)|获取此类的 `TypeDef` 元数据标记。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugClass` 接口表示未实例化的泛型类型。 ICorDebugType 接口表示一个实例化的泛型类型。 例如，`Hashtable<K, V>` 将由 `ICorDebugClass`表示，而 `Hashtable<Int32, String>` 将由 `ICorDebugType`表示。  
  
 非泛型类型由 `ICorDebugClass` 和 `ICorDebugType`表示。 后一种接口在 .NET Framework 版本2.0 中引入，用于处理类型实例化。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
