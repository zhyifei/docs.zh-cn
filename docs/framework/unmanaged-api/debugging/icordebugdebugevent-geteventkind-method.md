---
title: ICorDebugDebugEvent::GetEventKind 方法
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93dc268e65578a80fe8562f4c4d4fd71fa6db981
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711835"
---
# <a name="icordebugdebugeventgeteventkind-method"></a>ICorDebugDebugEvent::GetEventKind 方法
指出该 `ICorDebugDebugEvent` 对象代表的事件类型。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
#### <a name="parameters"></a>参数  
 p调试事件类型  
 一个指向[CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)枚举成员，用于指示事件的类型。  
  
## <a name="remarks"></a>备注  
 基于 `pDebugEventKind` 值，可调用 `QueryInterface` 以获取包含其他数据的精确度更高的调试事件接口。  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorDebugDebugEvent 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
