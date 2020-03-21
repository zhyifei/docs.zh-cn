---
title: IMetaDataImport::GetPropertyProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175325"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps 方法
获取指定令牌表示的属性的元数据。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,
   [out] LPCWSTR           szProperty,
   [in]  ULONG             cchProperty,
   [out] ULONG             *pchProperty,
   [out] DWORD             *pdwPropFlags,
   [out] PCCOR_SIGNATURE   *ppvSig,
   [out] ULONG             *pbSig,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,
   [out] mdMethodDef       *pmdGetter,
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,
   [out] ULONG             *pcOtherMethod
);  
```  
  
## <a name="parameters"></a>parameters  
 `prop`  
 [在]表示要为其返回元数据的属性的令牌。  
  
 `pClass`  
 [出]指向 TypeDef 令牌的指针，表示实现该属性的类型。  
  
 `szProperty`  
 [出]保存属性名称的缓冲区。  
  
 `cchProperty`  
 [在]以 宽字符表示`szProperty`的大小。  
  
 `pchProperty`  
 [出]在 中`szProperty`返回的宽字符数。  
  
 `pdwPropFlags`  
 [出]指向应用于该属性的任何属性标志的指针。 此值是[CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)枚举中的位掩码。  
  
 `ppvSig`  
 [出]指向属性的元数据签名的指针。  
  
 `pbSig`  
 [出]在 中`ppvSig`返回的字节数。  
  
 `pdwCPlusTypeFlag`  
 [出]指定作为属性默认值的常量类型的标志。 此值来自 CorElementType 枚举。  
  
 `ppDefaultValue`  
 [出]指向存储此属性的默认值的字节的指针。  
  
 `pcchDefaultValue`  
 [出]大字符的大小`ppDefaultValue`，如果`pdwCPlusTypeFlag`为ELEMENT_TYPE_STRING;否则，此值不相关。 在这种情况下，将从 指定的类型推断`ppDefaultValue`的长度`pdwCPlusTypeFlag`。  
  
 `pmdSetter`  
 [出]指向 MethodDef 令牌的指针，表示属性的设置访问器方法。  
  
 `pmdGetter`  
 [出]指向 MethodDef 令牌的指针，表示属性的 get 访问器方法。  
  
 `rmdOtherMethod`  
 [出]表示与属性关联的其他方法的 MethodDef 令牌数组。  
  
 `cMax`  
 [in] `rmdOtherMethod` 数组的最大大小。 如果提供的数组足够大以容纳所有方法，则不会发出警告即可跳过这些方法。  
  
 `pcOtherMethod`  
 [出]在 中`rmdOtherMethod`返回的 MethodDef 令牌数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
