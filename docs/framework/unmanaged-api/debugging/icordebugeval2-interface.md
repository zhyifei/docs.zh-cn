---
title: ICorDebugEval2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: e69b32430651edd0222db874e2659bd959f89549
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788711"
---
# <a name="icordebugeval2-interface"></a>ICorDebugEval2 接口

扩展 "ICorDebugEval" 以提供对泛型类型的支持。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CallParameterizedFunction 方法](icordebugeval2-callparameterizedfunction-method.md)|设置对指定的 "ICorDebugFunction" 的调用，该调用可以嵌套在其构造函数采用类型参数的类型内，也可以采用类型参数。|  
|[CreateValueForType 方法](icordebugeval2-createvaluefortype-method.md)|获取一个指针，该指针指向指定类型的新 "ICorDebugValue"，其初始值为 null 或零。|  
|[NewParameterizedArray 方法](icordebugeval2-newparameterizedarray-method.md)|分配指定元素类型和维度的新数组。|  
|[NewParameterizedObject 方法](icordebugeval2-newparameterizedobject-method.md)|实例化一个新的参数化类型对象，并调用该对象的构造函数方法。|  
|[NewParameterizedObjectNoConstructor 方法](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|实例化指定类的一个新参数化类型对象，而不尝试调用构造函数方法|  
|[NewStringWithLength 方法](icordebugeval2-newstringwithlength-method.md)|使用指定的内容创建指定长度的新字符串。|  
|[RudeAbort 方法](icordebugeval2-rudeabort-method.md)|中止此 `ICorDebugEval2` 当前正在执行的计算。|  
  
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
