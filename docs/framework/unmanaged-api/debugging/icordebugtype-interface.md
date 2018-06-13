---
title: ICorDebugType 接口 1
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
ms.openlocfilehash: de2871b406bb9da84d20d7c526ad4a703baae409
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422844"
---
# <a name="icordebugtype-interface1"></a>ICorDebugType 接口 1
表示类型，基本或复杂 （即，用户定义）。 如果该类型是泛型类型，则 `ICorDebugType` 表示未实例化的泛型类型。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumerateTypeParameters 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|获取的接口指针指向引用泛型 ICorDebugTypeEnum<xref:System.Type>的引用此类参数`ICorDebugType`。|  
|[GetBase 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|获取到的接口指针`ICorDebugType`引用所引用此类的基类`ICorDebugType`，如果存在。|  
|[GetClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|获取的接口指针指向引用此类型化的构造函数 ICorDebugClass `ICorDebugType`。|  
|[GetFirstTypeParameter 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|获取到的接口指针`ICorDebugType`引用的第一个泛型<xref:System.Type>引用此类的构造函数的参数`ICorDebugType`。|  
|[GetRank 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|获取一个数组类型中的维度数。|  
|[GetStaticFieldValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|令牌中指定的堆栈帧 ICorDebugValue 包含引用的指定字段的静态字段的值获取的接口指针。|  
|[GetType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|获取一个 CorElementType 值，描述公共语言运行时的本机类型<xref:System.Type>引用此`ICorDebugType`。|  
  
## <a name="remarks"></a>备注  
 如果类型是泛型，`ICorDebugClass`表示实例化的类型。 `ICorDebugType`接口表示实例化泛型类型。 例如，哈希表\<K，V > 将由表示`ICorDebugClass`，而哈希表\<Int32，字符串 > 将由表示`ICorDebugType`。  
  
 非泛型类型表示两个`ICorDebugClass`和`ICorDebugType`。 类型实例化处理.NET Framework 2.0 版中引入了后者的接口。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
