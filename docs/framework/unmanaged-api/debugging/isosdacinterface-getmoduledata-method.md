---
title: ISOSDacInterface::GetModuleData 方法
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 80b15f076dfe7a7bbbe7e28d9d68f01255e47202
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828583"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>ISOSDacInterface::GetModuleData 方法

获取对应于在给定地址加载该模块的数据。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

### <a name="parameters"></a>参数

`moduleAddr` [in]要检索其信息的模块的地址。

`data` [out][DacpModuleData 结构](dacpmoduledata-structure.md)来保存已加载模块的信息。


## <a name="remarks"></a>备注

提供的方法属于`ISOSDacInterface`接口，并对应于虚拟方法表 13 槽。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 无  
**库：** 无  
**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅

- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [ISOSDacInterface 接口](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
