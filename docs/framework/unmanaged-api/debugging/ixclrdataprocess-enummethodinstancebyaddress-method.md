---
title: IXCLR数据处理：：枚举方法实例按地址方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176651"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>IXCLR数据处理：：枚举方法实例按地址方法

枚举从地址偏移开始此过程的方法实例。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a>parameters

`handle`\
[在]用于枚举方法实例的句柄。

`mod`\
[出]枚举的方法实例。

## <a name="remarks"></a>备注

提供的方法是接口的一`IXCLRDataProcess`部分，对应于虚拟方法表的第 28 个插槽。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。
**标题：** 无**库：** 无 **.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>另请参阅

- [CLRDataSource 类型枚举](clrdatasourcetype-enumeration.md)
- [调试](index.md)
- [IXCLRDataProcess 接口](ixclrdataprocess-interface.md)
