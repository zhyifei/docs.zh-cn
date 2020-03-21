---
title: IMetaDataEmit::DefineField 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177703"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField 方法
为具有指定元数据签名的字段创建定义，并获取该字段定义的令牌。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a>parameters  
 `td`  
 [在]封闭`mdTypeDef`类或接口的令牌。  
  
 `szName`  
 [在]Unicode 中的字段名称。  
  
 `dwFieldFlags`  
 [在]字段属性。 这是值的`CorFieldAttr`位掩码。  
  
 `pvSigBlob`  
 [在]字段签名作为 BLOB。  
  
 `cbSigBlob`  
 [在]中的`pvSigBlob`字节计数。  
  
 `dwCPlusTypeFlag`  
 [在]常`ELEMENT_TYPE_`*\** 量值的 。 这是一个`CorElementType`值。 如果未为字段定义常量值，请使用`ELEMENT_TYPE_END`。  
  
 `pValue`  
 [在]字段的常量值。  
  
 `cchValue`  
 [在]的大小（Unicode）字符。 `pValue`  
  
 `pmd`  
 [出]分配的`mdFieldDef`令牌。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
