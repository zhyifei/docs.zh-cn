---
title: DacpReJitData 结构
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 46031f29da6916eeaeea863ebef6924a720d7155
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793818"
---
# <a name="dacprejitdata-structure"></a>DacpReJitData 结构

定义有关给定探查器检测到的方法的基本信息。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```cpp
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a>Members

| 成员           | 描述                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | 方法的 ReJit 修订号。                                                          |
| `flags`          | 一个标志，指示给定版本的该方法的 ReJit 检测的当前状态。 |
| `NativeCodeAddr` | 该方法的 rejitted 实现的基址。                                         |

## <a name="remarks"></a>备注

此结构存在于运行时中，并且不会通过任何标头或库文件公开。 若要使用它，请定义上面指定的结构。 如果不使用 Microsoft 编译器，还必须使用 `ms_struct` 封装来定义结构。

## <a name="requirements"></a>需求
**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 内容  
**库：** 内容  
**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>另请参阅

- [调试](index.md)
- [调试结构](debugging-structures.md)
