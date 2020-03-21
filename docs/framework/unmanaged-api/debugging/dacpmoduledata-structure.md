---
title: DacpModuleData 结构
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179192"
---
# <a name="dacpmoduledata-structure"></a>DacpModuleData 结构

为模块的运行时信息定义传输缓冲区。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a>成员

| 成员    | 说明                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | 模块对象的地址。                                           |
| `File`    | 指向可移植可执行文件 （PE） 文件的指针。                       |
| `ilBase`  | 加载图像的基的地址。                                 |
| `payLoad` | 用于运行时使用的其他模块信息的有效负载缓冲区。 |

## <a name="remarks"></a>备注

此结构位于运行时内，不会通过任何标头或库文件公开。 要使用它，请定义上面指定的结构。

## <a name="requirements"></a>要求
**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
**标题：** 没有  
**库：** 没有  
**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>另请参阅

- [调试](index.md)
- [调试结构](debugging-structures.md)
