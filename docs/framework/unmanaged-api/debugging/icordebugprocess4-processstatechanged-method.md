---
title: ICorDebugProcess4::ProcessStateChanged 方法
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
ms.openlocfilehash: adfd563e19389642ac0ed0a3cef4aae8a32fa466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767182"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::ProcessStateChanged 方法

通知 ICorDebug 管道的过程调试器扩展继续调试对象的执行。

## <a name="syntax"></a>语法

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>参数

 `eChange`\
[in]成员[CorDebugStateChange 枚举](cordebugstatechange-enumeration.md)描述进程的执行状态的更改。

## <a name="remarks"></a>备注

提供的方法属于`ICorDebugProcess4`接口，并对应于虚拟方法表的第四个槽。

## <a name="requirements"></a>要求

 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。

 **标头：** 无

 **库：** 无
 
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>请参阅

- [ICorDebugProcess4 接口](icordebugprocess4-interface.md)
- [调试接口](debugging-interfaces.md)
- [调试](index.md)
