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
ms.openlocfilehash: c901e21521e941c51939958175a5316808890e9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208611"
---
# <a name="icordebughandlevalue-interface"></a>ICorDebugHandleValue 接口

ICorDebugReferenceValue 的子类，表示调试器已为其创建了垃圾回收句柄的引用值。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Dispose 方法](icordebughandlevalue-dispose-method.md)|释放此对象所引用的句柄， `ICorDebugHandleValue` 而不显式释放接口指针。|  
|[GetHandleType 方法](icordebughandlevalue-gethandletype-method.md)|获取一个 CorDebugHandleType 值，该值描述此所引用的句柄的类型 `ICorDebugHandleValue` 。|  
  
## <a name="remarks"></a>备注  
 当 `ICorDebugReferenceValue` 执行调试的代码时，对象会失效。 `ICorDebugHandleValue`通过中断和继续来维护其引用，直到显式释放它。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](debugging-interfaces.md)
