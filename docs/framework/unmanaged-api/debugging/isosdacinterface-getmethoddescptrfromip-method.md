---
title: ISOSDacInterface::GetMethodDescPtrFromIP 方法
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 74853733b1fb7f023d9f192d3e862dbf6875ecda
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828597"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a>ISOSDacInterface::GetMethodDescPtrFromIP 方法

检索对应的方法，其中包含给定的本机指令地址 MethodDesc 的指针。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

### <a name="parameters"></a>参数

`ip` [in]在运行时方法中的地址。

`ppMD` [out]地址`MethodDesc`特定方法。

## <a name="remarks"></a>备注

提供的方法属于[`ISOSDacInterface`接口](isosdacinterface-interface.md)和对应于虚拟方法表 21 槽。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 无  
**库：** 无  
**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅

- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [ISOSDacInterface 接口](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
