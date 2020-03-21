---
title: IMetaDataEmit::SetEventProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177530"
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps 方法
设置或更新由之前调用[IMetaDataEmit：:DefineEvent）](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)定义的事件的指定功能。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>parameters  
 `ev`  
 [在]事件令牌。  
  
 `dwEventFlags`  
 [在]事件标志。 这是值的`CorEventAttr`位掩码。  
  
 `tkEventType`  
 [在]事件类的令牌。 这是 或`mdTypeDef``mdTypeRef`标记。  
  
 `mdAddOn`  
 [在]用于订阅事件或 null 的方法。  
  
 `mdRemoveOn`  
 [在]用于取消订阅事件或 null 的方法。  
  
 `mdFire`  
 [在]用于（由派生类）引发事件的方法。  
  
 `rmdOtherMethods[]`  
 [在]与事件关联的其他方法的令牌数组。 数组的最后一个元素必须是`mdMethodDefNil`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
