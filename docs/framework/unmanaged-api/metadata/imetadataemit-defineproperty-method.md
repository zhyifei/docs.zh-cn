---
title: IMetaDataEmit::DefineProperty 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: f11b374ed0ecbfc137c43fb641ae691237604691
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431518"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty 方法
使用指定的 `get` 和 `set` 方法访问器创建指定类型的属性定义，并获取该属性定义的标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>参数  
 `td`  
 中正在为其定义属性的类或接口的标记。  
  
 `szProperty`  
 中属性的名称。  
  
 `dwPropFlags`  
 中属性标志。  
  
 `pvSig`  
 中属性签名。  
  
 `cbSig`  
 中`pvSig`中的字节计数。  
  
 `dwCPlusTypeFlag`  
 中属性的默认值的类型。  
  
 `pValue`  
 中属性的默认值。  
  
 `cchValue`  
 中`pValue`中的（Unicode）字符的计数。  
  
 `mdSetter`  
 中用于设置属性值的方法。  
  
 `mdGetter`  
 中获取属性值的方法。  
  
 `rmdOtherMethods[]`  
 中与属性关联的其他方法的数组。 使用 `mdTokenNil`终止数组。  
  
 `pmdProp`  
 弄分配 `mdProperty` 标记。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
