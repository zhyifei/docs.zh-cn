---
title: “Cor调试状态已更改”枚举
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
ms.openlocfilehash: 239e3a82df0e6010278669f9f429bfad0d163319
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133722"
---
# <a name="cordebugstatechange-enumeration"></a>“Cor调试状态已更改”枚举

描述基于进程变化必须删除的缓存数据数量。

## <a name="syntax"></a>语法

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a>Members

| 成员            | 描述                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | 该进程向前执行，达到了一种新的内存状态。            |
| `FLUSH_ALL`       | 进程的内存可能与以往截然不同。 |

## <a name="remarks"></a>备注

 当调试器使用[ICorDebugProcess4：:P rocessstatechanged](icordebugprocess4-processstatechanged-method.md)或[ICorDebugProcess6：:P rocessstatechanged](icordebugprocess6-processstatechanged-method.md)调用 `ProcessStateChanged` 方法时，`CorDebugStateChange` 枚举的成员作为参数提供。

## <a name="requirements"></a>要求

 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。

 **标头**：CorDebug.idl、CorDebug.h

 **库：** CorGuids.lib

 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>请参阅

- [调试枚举](debugging-enumerations.md)
- [调试](index.md)
