---
title: ICorDebugClass2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: ff15297eb479f7474c9f07123a29263fb4da3205
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893976"
---
# <a name="icordebugclass2-interface"></a>ICorDebugClass2 接口

表示泛型类或具有 <xref:System.Type> 类型的方法参数的类。 此接口扩展[ICorDebugClass](icordebugclass-interface.md)。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetParameterizedType 方法](icordebugclass2-getparameterizedtype-method.md)|获取此类的类型声明。|  
|[SetJMCStatus 方法](icordebugclass2-setjmcstatus-method.md)|对于此类的每个方法，设置一个值，该值指示该方法是否为用户定义的代码。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugClass 接口](icordebugclass-interface.md)
- [调试接口](debugging-interfaces.md)
