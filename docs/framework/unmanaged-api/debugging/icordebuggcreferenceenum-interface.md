---
title: ICorDebugGCReferenceEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: 49f89f7d36e74b1fa5921230d7dc6d271d4c0883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134633"
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum 接口
提供针对将进行垃圾回收的对象的枚举器。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Next 方法](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|获取指定数量的[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)实例，其中包含有关将进行垃圾回收的对象的信息。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugGCReferenceEnum` 接口实现 "ICorDebugEnum" 接口。  
  
 `ICorDebugGCReferenceEnum` 实例通过调用[ICorDebugProcess5：： EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)方法填充[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)实例。 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)对象可通过调用[ICorDebugGCReference：： Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)方法进行枚举。  
  
 此方法填充的集合中的[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)对象表示三种对象：  
  
- 所有托管堆栈中的对象。 这包括托管代码中的实时引用以及由公共语言运行时创建的对象。  
  
- 句柄表中的对象。 这包括模块中的强引用（`HNDTYPE_STRONG` 和 `HNDTYPE_REFCOUNT`）和静态变量。  
  
- 终结器队列中的对象。 终结器队列根对象，直到终结器运行。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
