---
title: IXCLRDataMethodDefinition::EndEnumInstances 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4a7cd8850778e9bbbc7d8d67f464c7787e40bc13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566084"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a>IXCLRDataMethodDefinition::EndEnumInstances 方法

释放使用的内部实例枚举过程中使用的迭代器的资源。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a>参数

`handle` [out]枚举的实例句柄。

## <a name="remarks"></a>备注

提供的方法属于`IXCLRDataMethodDefinition`接口，并对应于虚拟方法表的第五个槽。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 无  
**库：** 无  
**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅

- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [IXCLRDataMethodDefinition 接口](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
