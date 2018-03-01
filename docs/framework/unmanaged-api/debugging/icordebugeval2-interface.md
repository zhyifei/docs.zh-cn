---
title: "ICorDebugEval2 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ac816d2b2dce6c9c76813bf4247bac7ca40da5f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2-interface1"></a>ICorDebugEval2 接口 1
扩展"ICorDebugEval"以对泛型类型提供支持。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CallParameterizedFunction 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|设置指定"ICorDebugFunction"，这可以嵌套在其构造函数采用类型参数或本身可以采用类型参数的类型调用。|  
|[CreateValueForType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|获取一个指向新的"ICorDebugValue"的指定类型，使用的初始值为 null 或零。|  
|[NewParameterizedArray 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|分配的指定的元素类型和维度的一个新数组。|  
|[NewParameterizedObject 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|实例化一个新的参数化的类型对象并调用对象的构造函数方法。|  
|[NewParameterizedObjectNoConstructor 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|要指定的类的新参数化的类型对象但不尝试调用构造函数方法实例化|  
|[NewStringWithLength 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|具有指定内容创建新字符串，指定的长度。|  
|[RudeAbort 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|中止计算此`ICorDebugEval2`当前正在执行。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
