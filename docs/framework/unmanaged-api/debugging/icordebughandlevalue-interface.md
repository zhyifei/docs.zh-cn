---
title: ICorDebugHandleValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: 94472e84b73cdffe09505088b1e7fbc20a209bc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138481"
---
# <a name="icordebughandlevalue-interface"></a>ICorDebugHandleValue 接口

ICorDebugReferenceValue 的子类，表示调试器已为其创建了垃圾回收句柄的引用值。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Dispose 方法](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|释放此 `ICorDebugHandleValue` 对象所引用的句柄，无需显式释放接口指针。|  
|[GetHandleType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|获取一个 CorDebugHandleType 值，该值描述此 `ICorDebugHandleValue`引用的句柄的类型。|  
  
## <a name="remarks"></a>备注  
 当执行调试的代码时，`ICorDebugReferenceValue` 对象将会失效。 `ICorDebugHandleValue` 通过中断和继续来维护其引用，直到显式释放它。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
