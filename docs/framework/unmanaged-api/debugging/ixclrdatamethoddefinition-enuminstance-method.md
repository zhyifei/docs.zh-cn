---
title: IXCLRDataMethodDefinition::EnumInstance 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0fbb246f8c4bf791dd705aedf8eab6ef8bfeae56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680255"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a>IXCLRDataMethodDefinition::EnumInstance 方法

枚举该方法定义的实例。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

### <a name="parameters"></a>参数

`handle` [in、 out]枚举的实例句柄。

`instance` [out]枚举的实例。

## <a name="remarks"></a>备注

提供的方法属于`IXCLRDataMethodDefinition`接口，并对应于虚拟方法表的第四个槽。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 无  
**库：** 无  
**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅

- [CLRDataSourceType 枚举](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [IXCLRDataMethodDefinition 接口](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [IXCLRDataMethodInstance 接口](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
