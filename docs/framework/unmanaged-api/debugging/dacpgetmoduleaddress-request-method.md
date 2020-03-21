---
title: DacpGetModule 地址：请求方法
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179203"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModule 地址：请求方法

执行请求，从给定的运行时结构填充结构。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>parameters

`pDataModule`\
[在]指向种子数据模块的指针。

## <a name="remarks"></a>备注

此结构位于运行时内，不会通过任何标头或库文件公开。 要使用它，最简单的方法是模拟实现：

- 使用以下参数返回从调用`Request``IXCLRDataModule*`参数上的方法获得的值：`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>要求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
**标题：** 无**库：** 无  
**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>另请参阅

- [调试](index.md)
- [达格格获取模块地址接口](dacpgetmoduleaddress-structure.md)
