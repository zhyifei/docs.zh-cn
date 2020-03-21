---
title: ICorDebugProcess4：:Process状态更改方法
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178629"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4：:Process状态更改方法

通知 ICorDebug 管道进程外调试器正在继续执行调试器。

## <a name="syntax"></a>语法

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>parameters

 `eChange`\
[在][CorDebugStateChange 计数](cordebugstatechange-enumeration.md)的成员，描述进程执行状态的变化。

## <a name="remarks"></a>备注

提供的方法是接口的一`ICorDebugProcess4`部分，对应于虚拟方法表的第四个槽。

## <a name="requirements"></a>要求

 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。

 **标题：** 没有

 **库：** 没有

 **.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>另请参阅

- [ICorDebugProcess4 接口](icordebugprocess4-interface.md)
- [调试接口](debugging-interfaces.md)
- [调试](index.md)
