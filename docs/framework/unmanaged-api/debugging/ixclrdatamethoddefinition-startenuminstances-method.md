---
title: IXCLRDataMethodDefinition::StartEnumInstances 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7f45a5b13e767fa6849f307ee96fb822447f1263
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629953"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a>IXCLRDataMethodDefinition::StartEnumInstances 方法

提供一个句柄的方法实例枚举给定`IXCLRDataAppDomain`。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>参数

`appDomain`\
[in]枚举 AppDomain。

`handle`\
[out]枚举的实例句柄。

## <a name="remarks"></a>备注

提供的方法属于`IXCLRDataMethodDefinition`接口，并对应于虚拟方法表的第三个槽。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** None  
**库：** None  
**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅

- [CLRDataSourceType 枚举](clrdatasourcetype-enumeration.md)
- [调试](index.md)
- [IXCLRDataMethodDefinition 接口](ixclrdatamethoddefinition-interface.md)
