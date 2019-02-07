---
title: ISOSDacInterface::GetMethodDescData 方法
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 47cea4810b764005e87d00966c15cf138f5913a7
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825948"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>ISOSDacInterface::GetMethodDescData 方法

获取给定 MethodDesc 指针的数据。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

### <a name="parameters"></a>参数

`methodDesc` [in]MethodDesc 的地址。

`ip` [in]该方法的 IP 地址。

`data` [out]返回从内部 Api 与 MethodDesc 关联的数据。

`cRevertedRejitVersions` [out]已还原的 rejit 版本数。

`rgRevertedRejitData` [out]返回从内部 Api 与已还原的 rejit 版本关联的数据。

`pcNeededRevertedRejitData` [out]存储与已还原的 ReJit 版本关联的数据所需的字节数。

## <a name="remarks"></a>备注

提供的方法属于`ISOSDacInterface`接口，并对应于虚拟方法表的 20 槽。 若要能够使用它们[ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md)必须定义为 64 位无符号整数。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 无  
**库：** 无  
**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅

- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [ISOSDacInterface 接口](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
