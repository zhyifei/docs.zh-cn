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
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175845"
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent 方法
为具有指定元数据签名的事件创建定义，并获取该事件定义的令牌。  
  
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
  
## <a name="parameters"></a>parameters  
 `td`  
 [在]目标类或接口的令牌。 这是 或`mdTypeDef``mdTypeDefNil`标记。  
  
 `szEvent`  
 [在]事件的名称。  
  
 `dwEventFlags`  
 [在]事件标志。  
  
 `tkEventType`  
 [在]事件类的令牌。 这是 一`mdTypeDef`个`mdTypeRef`、或`mdTokenNil`标记。  
  
 `mdAddOn`  
 [在]用于订阅事件或 null 的方法。  
  
 `mdRemoveOn`  
 [在]用于取消订阅事件或 null 的方法。  
  
 `mdFire`  
 [在]用于（由派生类）引发事件的方法。  
  
 `rmdOtherMethods[]`  
 [在]与事件关联的其他方法的令牌数组。 数组用`mdMethodDefNil`令牌终止。  
  
 `pmdEvent`  
 [出]分配给事件的元数据令牌。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
