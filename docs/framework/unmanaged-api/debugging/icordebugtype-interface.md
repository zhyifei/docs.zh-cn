---
title: ICorDebugType 接口
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964761"
---
# <a name="icordebugtype-interface"></a>ICorDebugType 接口
表示基本或复杂类型 (即用户定义的类型)。 如果该类型是泛型类型，则 `ICorDebugType` 表示未实例化的泛型类型。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumerateTypeParameters 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|获取一个接口指针, 该指针指向引用此<xref:System.Type> `ICorDebugType`所引用类的泛型参数的 ICorDebugTypeEnum。|  
|[GetBase 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|获取一个接口指针, `ICorDebugType`该指针指向引用此引用的类 (如果存在此`ICorDebugType`类) 的基类。|  
|[GetClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|获取一个接口指针, 该指针指向引用此`ICorDebugType`的类型化构造函数的 ICorDebugClass。|  
|[GetFirstTypeParameter 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|获取一个接口指针`ICorDebugType` , 该指针指向引用此`ICorDebugType`引用<xref:System.Type>的类的构造函数的第一个泛型参数。|  
|[GetRank 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|获取数组类型中的维度数。|  
|[GetStaticFieldValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|获取一个指向 ICorDebugValue 的接口指针, 该指针包含指定的堆栈帧中指定字段标记所引用的静态字段的值。|  
|[GetType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|获取一个 CorElementType 值, 该值描述此<xref:System.Type> `ICorDebugType`所引用的公共语言运行时的本机类型。|  
  
## <a name="remarks"></a>备注  
 如果类型为泛型, `ICorDebugClass`则表示未实例化的类型。 `ICorDebugType`接口表示一个实例化的泛型类型。 例如, 哈希\<表 K, V > 将由`ICorDebugClass`表示, 而哈\<希表`ICorDebugType`Int32, 字符串 > 将由表示。  
  
 非泛型类型由`ICorDebugClass`和`ICorDebugType`表示。 后一种接口在 .NET Framework 版本2.0 中引入, 用于处理类型实例化。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
