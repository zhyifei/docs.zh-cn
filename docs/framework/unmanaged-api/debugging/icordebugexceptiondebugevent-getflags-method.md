---
title: ICorDebugExceptionDebugEvent::GetFlags 方法
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 5793d939c8497ef842f614048707f69faa8ac568
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976039"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a>ICorDebugExceptionDebugEvent::GetFlags 方法
获取指示是否可拦截异常的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `pdwFlags`  
 弄指向[CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md)值的指针，该指针指示是否可以截获异常。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [“ICor调试异常调试事件”接口](icordebugexceptiondebugevent-interface.md)
- [调试接口](debugging-interfaces.md)
