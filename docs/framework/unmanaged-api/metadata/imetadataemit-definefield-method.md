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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 057bae1d702fa091ebc3d3178c9fba35d5dd3d90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777654"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField 方法
使用指定的元数据签名中，创建一个字段的定义并获取该字段定义的标记。  
  
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
  
## <a name="parameters"></a>参数  
 `td`  
 [in]`mdTypeDef`令牌对封闭类或接口。  
  
 `szName`  
 [in]Unicode 中的字段名称。  
  
 `dwFieldFlags`  
 [in]字段特性。 这是一个位掩码的`CorFieldAttr`值。  
  
 `pvSigBlob`  
 [in]作为 BLOB 字段签名。  
  
 `cbSigBlob`  
 [in]中的字节计数`pvSigBlob`。  
  
 `dwCPlusTypeFlag`  
 [in]`ELEMENT_TYPE_` *\** 的常量值。 这是`CorElementType`值。 如果不定义该字段的常数值，使用`ELEMENT_TYPE_END`。  
  
 `pValue`  
 [in]字段的常量值。  
  
 `cchValue`  
 [in] (Unicode) 字符中的大小`pValue`。  
  
 `pmd`  
 [out]`mdFieldDef`分配标记。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
