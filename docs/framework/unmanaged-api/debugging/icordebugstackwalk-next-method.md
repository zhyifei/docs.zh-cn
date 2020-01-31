---
title: ICorDebugStackWalk::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: b76d17337408653d130ee0cb8594e759bdade37c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791872"
---
# <a name="icordebugstackwalknext-method"></a>ICorDebugStackWalk::Next 方法
将[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象移动到下一帧。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|运行时成功地展开为下一帧（请参阅 "备注"）。|  
|E_FAIL|`ICorDebugStackWalk` 对象不是高级对象。|  
|CORDBG_S_AT_END_OF_STACK|由于此展开导致堆栈结束。|  
|CORDBG_E_PAST_END_OF_STACK|帧指针已位于堆栈末尾;因此，不能访问其他帧。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 仅当运行时可以展开当前帧时，`Next` 方法才将 `ICorDebugStackWalk` 对象前进到调用帧。 否则，对象会前进到运行时能够展开的下一帧。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugStackWalk 接口](icordebugstackwalk-interface.md)
- [调试接口](debugging-interfaces.md)
- [调试](index.md)
