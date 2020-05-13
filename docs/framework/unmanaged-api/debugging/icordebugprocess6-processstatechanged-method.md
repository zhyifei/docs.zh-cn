---
title: ICorDebugProcess6::ProcessStateChanged 方法
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 6be216741e902b15efc3a3ece95cb4a4229960e3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212837"
---
# <a name="icordebugprocess6processstatechanged-method"></a>ICorDebugProcess6::ProcessStateChanged 方法
通知[ICorDebug](icordebug-interface.md)进程正在运行。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a>参数  
 `change`  
 中[ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)枚举的成员  
  
## <a name="remarks"></a>备注  
 调试器调用此方法来通知[ICorDebug](icordebug-interface.md)进程正在运行。  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [“ICor调试进程6”接口](icordebugprocess6-interface.md)
- [调试接口](debugging-interfaces.md)
