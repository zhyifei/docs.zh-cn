---
title: ICorDebugDebugEvent::GetThread Method
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: acce18517c105739417fc734b49ff004ca9546dc
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976373"
---
# <a name="icordebugdebugeventgetthread-method"></a>ICorDebugDebugEvent::GetThread Method
获取发生事件的线程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a>参数  
 ppThread  
 [输出] 指针指向代表事件发生线程的 ICorDebugThread 对象的地址。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [“ICor调试调试事件”接口](icordebugdebugevent-interface.md)
- [调试接口](debugging-interfaces.md)
