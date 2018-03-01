---
title: "IMetaDataEmit::DefineField 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e2c4b5604c3daec78744eb8902a30750571b9f82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField 方法
使用指定的元数据签名中，创建一个字段的定义并获取指向该字段定义的标记。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `td`  
 [in]`mdTypeDef`令牌对封闭类或接口。  
  
 `szName`  
 [in]Unicode 中的字段名称。  
  
 `dwFieldFlags`  
 [in]中的字段特性。 这是一个位掩码的`CorFieldAttr`值。  
  
 `pvSigBlob`  
 [in]作为 BLOB 的字段签名。  
  
 `cbSigBlob`  
 [in]中的字节计数`pvSigBlob`。  
  
 `dwCPlusTypeFlage`  
 [in]`ELEMENT_TYPE_`  *\** 的常量值。 这是`CorElementType`值。 如果不定义字段的常量值，使用`ELEMENT_TYPE_END`。  
  
 `pValue`  
 [in]字段的常量值。  
  
 `cchValue`  
 [in]以 (Unicode) 字符为单位的大小`pValue`。  
  
 `pmd`  
 [out]`mdFieldDef`分配的令牌。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
