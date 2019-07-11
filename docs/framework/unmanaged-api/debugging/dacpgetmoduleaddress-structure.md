---
title: DacpGetModuleAddress Structure
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 145b06f89b45b165b9d6329a4c16ac5739406113
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739192"
---
# <a name="dacpgetmoduleaddress-structure"></a>DacpGetModuleAddress Structure

定义模块地址请求的容器。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a>成员

| 成员      | 描述                |
| ----------- | -------------------------- |
| `ModulePtr` | 指向模块的指针。 |

## <a name="methods"></a>方法

| 方法                                                                                               | 描述                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [请求](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | 执行请求以填充从给定的运行时结构的结构。 |

## <a name="remarks"></a>备注

此结构存在于运行时内，不通过任何标头或库文件公开。 若要使用它，将结构定义为指定更高版本，其中`CLRDATA_ADDRESS`是 64 位无符号的整数。

## <a name="requirements"></a>要求
**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 无  
**库：** 无  
**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅

- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
