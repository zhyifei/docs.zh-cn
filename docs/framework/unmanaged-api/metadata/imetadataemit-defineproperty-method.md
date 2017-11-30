---
title: "IMetaDataEmit::DefineProperty 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineProperty
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc0403fd51f028510eb60d93ff96fc7d05606366
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty 方法
创建指定类型的属性定义具有指定`get`和`set`方法访问器中，并获取指向该属性定义的标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
#### <a name="parameters"></a>参数  
 `td`  
 [in]为类或接口在其定义的属性标记。  
  
 `szProperty`  
 [in]属性的名称。  
  
 `dwPropFlags`  
 [in]属性的标志。  
  
 `pvSig`  
 [in]属性签名中。  
  
 `cbSig`  
 [in]中的字节计数`pvSig`。  
  
 `dwCPlusTypeFlag`  
 [in]属性的默认值的类型。  
  
 `pValue`  
 [in]属性的默认值。  
  
 `cchValue`  
 [in]中的字符 (Unicode) 的计数`pValue`。  
  
 `mdSetter`  
 [in]用于设置属性值的方法。  
  
 `mdGetter`  
 [in]获取属性值的方法。  
  
 `rmdOtherMethods[]`  
 [in]与属性关联的其他方法的数组。 终止与数组`mdTokenNil`。  
  
 `pmdProp`  
 [out]`mdProperty`分配的令牌。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
