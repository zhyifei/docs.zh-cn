---
title: IXCLRDataModule::GetMethodDefinitionByToken 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1371b86f30324908a639b3b1bbae0ae007ba590a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708085"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a>IXCLRDataModule::GetMethodDefinitionByToken 方法

获取与给定的元数据标记相对应的方法定义。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>语法

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

### <a name="parameters"></a>参数

`token` [in]方法标记中。

`methodDefinition` [out]方法定义中。

## <a name="remarks"></a>备注

提供的方法属于`IXCLRDataModule`接口，并对应于虚拟方法表 25 槽。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 无  
**库：** 无  
**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
 
## <a name="see-also"></a>请参阅

- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [IXCLRDataModule 接口](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
