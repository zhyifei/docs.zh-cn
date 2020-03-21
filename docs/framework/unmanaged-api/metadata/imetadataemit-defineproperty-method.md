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
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175780"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty 方法
使用指定的`get`和方法`set`访问器为指定类型创建属性定义，并获取该属性定义的令牌。  
  
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
  
## <a name="parameters"></a>parameters  
 `td`  
 [在]正在定义属性的类或接口的令牌。  
  
 `szProperty`  
 [在]属性的名称。  
  
 `dwPropFlags`  
 [在]属性标志。  
  
 `pvSig`  
 [在]属性签名。  
  
 `cbSig`  
 [在]中的`pvSig`字节计数。  
  
 `dwCPlusTypeFlag`  
 [在]属性的默认值的类型。  
  
 `pValue`  
 [在]属性的默认值。  
  
 `cchValue`  
 [在]中的（Unicode） 字符的`pValue`计数。  
  
 `mdSetter`  
 [在]设置属性值的方法。  
  
 `mdGetter`  
 [在]获取属性值的方法。  
  
 `rmdOtherMethods[]`  
 [在]与 属性关联的其他方法的数组。 使用 终止数组`mdTokenNil`。  
  
 `pmdProp`  
 [出]分配的`mdProperty`令牌。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
