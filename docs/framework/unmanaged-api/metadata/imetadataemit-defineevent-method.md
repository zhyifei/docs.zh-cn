---
title: IMetaDataEmit::DefineEvent 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: 7babd0a90b9882acb03b6360753f55c57a399b9e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005617"
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent 方法
使用指定的元数据签名创建事件的定义，并获取该事件定义的标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a>参数  
 `td`  
 中目标类或接口的标记。 这是 `mdTypeDef` 或 `mdTypeDefNil` 令牌。  
  
 `szEvent`  
 中事件的名称。  
  
 `dwEventFlags`  
 中事件标志。  
  
 `tkEventType`  
 中事件类的标记。 这是 `mdTypeDef` 、 `mdTypeRef` 或 `mdTokenNil` 标记。  
  
 `mdAddOn`  
 中用于订阅事件的方法，或为 null。  
  
 `mdRemoveOn`  
 中用于取消订阅事件的方法，或为 null。  
  
 `mdFire`  
 中使用的方法（由派生类）引发事件。  
  
 `rmdOtherMethods[]`  
 中与事件关联的其他方法的标记数组。 使用标记终止数组 `mdMethodDefNil` 。  
  
 `pmdEvent`  
 弄分配给事件的元数据标记。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit 接口](imetadataemit-interface.md)
- [IMetaDataEmit2 接口](imetadataemit2-interface.md)
