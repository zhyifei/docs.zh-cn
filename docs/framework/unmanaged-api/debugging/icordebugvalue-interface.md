---
title: ICorDebugValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: 77d28d8eef97a934c15ac29725f856f4bf39e6ce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140154"
---
# <a name="icordebugvalue-interface"></a>ICorDebugValue 接口
表示正在调试的进程中的值。 该值可以是读取或写入值。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateBreakpoint 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|当前未实现此方法。|  
|[GetAddress 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|获取此 `ICorDebugValue` 对象的地址，该对象处于调试过程中。|  
|[GetSize 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|获取此 `ICorDebugValue` 对象的大小（以字节为单位）。|  
|[GetType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|获取此 `ICorDebugValue` 对象的基元类型。|  
  
## <a name="remarks"></a>备注  
 通常，值对象的所有权在返回时传递。 当对象使用完对象后，接收方负责从对象中删除引用。  
  
 根据从何处检索值，在恢复进程后，值可能不会保持有效。 因此，通常情况下，不应在对[ICorDebugController：： Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)方法的调用中保存值。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugValue3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
