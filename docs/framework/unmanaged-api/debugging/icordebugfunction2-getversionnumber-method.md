---
title: ICorDebugFunction2::GetVersionNumber 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
ms.openlocfilehash: 5826297d8151cf05e1ec08acbf5c9cd381d2452b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137804"
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber 方法
获取此函数的 "编辑并继续" 版本。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a>参数  
 `pnVersion`  
 弄指向一个整数的指针，该整数是此 ICorDebugFunction2 对象所表示的函数的版本号。  
  
## <a name="remarks"></a>备注  
 运行时跟踪在调试会话期间对每个模块进行的编辑的次数。 函数的版本号比引入函数的编辑次数多一个。 函数的原始版本是版本1。 每次调用该模块上的[ICorDebugModule2：： ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)时，模块的数字都会递增。 因此，如果在第一次调用和第三次 `ICorDebugModule2::ApplyChanges`调用时已替换函数体，则 `GetVersionNumber` 可能返回该函数的版本1、2或4，但不返回版本3。 （该函数不会有版本3。）  
  
 为每个模块单独跟踪版本号。 因此，如果在模块1上执行四个编辑，而在模块2上执行 "无"，则下一次编辑时，模块1将为模块1中的所有编辑函数分配6号。 如果相同的编辑触及模块2，则模块2中的函数将获得版本号2。  
  
 `GetVersionNumber` 方法获取的版本号可能低于[ICorDebugFunction：： GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)获取的版本号。  
  
 [ICorDebugCode：： GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)方法执行与 `ICorDebugFunction2::GetVersionNumber`相同的操作。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
