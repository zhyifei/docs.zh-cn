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
ms.openlocfilehash: 247a2793bf3806f5ee38585d50b4535820dfcb69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437055"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps 方法
获取由指定标记表示的属性的元数据。  
  
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
  
## <a name="parameters"></a>参数  
 `prop`  
 中一个标记，它表示要为其返回元数据的属性。  
  
 `pClass`  
 弄一个指针，指向表示实现属性的类型的 TypeDef 标记。  
  
 `szProperty`  
 弄用于保存属性名称的缓冲区。  
  
 `cchProperty`  
 中`szProperty`的大小（以宽字符为大小）。  
  
 `pchProperty`  
 弄`szProperty`中返回的宽字符数。  
  
 `pdwPropFlags`  
 弄指向应用于属性的任何属性标志的指针。 此值是[CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)枚举中的位掩码。  
  
 `ppvSig`  
 弄指向属性的元数据签名的指针。  
  
 `pbSig`  
 弄`ppvSig`中返回的字节数。  
  
 `pdwCPlusTypeFlag`  
 弄一个标志，该标志指定作为属性的默认值的常量的类型。 此值来自 CorElementType 枚举。  
  
 `ppDefaultValue`  
 弄指向存储此属性的默认值的字节的指针。  
  
 `pcchDefaultValue`  
 弄如果 ELEMENT_TYPE_STRING `pdwCPlusTypeFlag`，则为 `ppDefaultValue`的宽字符大小;否则，此值是不相关的。 在这种情况下，将从 `pdwCPlusTypeFlag`指定的类型推断 `ppDefaultValue` 的长度。  
  
 `pmdSetter`  
 弄一个指针，它指向表示属性的 set 访问器方法的 MethodDef 标记。  
  
 `pmdGetter`  
 弄一个指针，它指向表示属性的 get 访问器方法的 MethodDef 标记。  
  
 `rmdOtherMethod`  
 弄MethodDef 标记的数组，表示与属性关联的其他方法。  
  
 `cMax`  
 [in] `rmdOtherMethod` 数组的最大大小。 如果未提供足够大的数组来容纳所有方法，则会跳过这些方法，而不发出警告。  
  
 `pcOtherMethod`  
 弄`rmdOtherMethod`中返回的 MethodDef 标记的数目。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
