---
title: ICorDebugValue3::GetSize64 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: 7ae06d825565faff70b0c8be2ccbee5228737e41
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791102"
---
# <a name="icordebugvalue3getsize64-method"></a>ICorDebugValue3::GetSize64 方法
获取此[ICorDebugValue3](icordebugvalue3-interface.md)对象的大小（以字节为单位）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a>参数  
 pSize  
 弄一个指针，指向该对象的大小（以字节为单位）。  
  
## <a name="remarks"></a>备注  
 如果此值的类型为引用类型，则此方法返回指针的大小，而不是对象的大小。  
  
 `ICorDebugValue3::GetSize` 方法与其输出参数类型中的[ICorDebugValue：： GetSize](icordebugvalue-getsize-method.md)方法不同。 在[ICorDebugValue：： GetSize](icordebugvalue-getsize-method.md)中，output 参数是 `ULONG32`;在 `ICorDebugValue3::GetSize`中，它是一个 `ULONG64`。 这使[ICorDebugValue3](icordebugvalue3-interface.md)接口可以报告超过2gb 的数组的大小。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugValue3 接口](icordebugvalue3-interface.md)
- [调试接口](debugging-interfaces.md)
