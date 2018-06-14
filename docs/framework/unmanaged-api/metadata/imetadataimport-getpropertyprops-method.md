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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7312cbd31a04365801b0380d5914966f36679560
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449450"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps 方法
获取指定标记所表示的属性的元数据。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `prop`  
 [in]一个表示要返回的元数据的属性的令牌。  
  
 `pClass`  
 [out]指向表示实现属性的类型的 TypeDef 标记的指针。  
  
 `szProperty`  
 [out]一个缓冲区来容纳属性名。  
  
 `cchProperty`  
 [in]在宽字符为单位的大小`szProperty`。  
  
 `pchProperty`  
 [out]在中返回的宽字符数`szProperty`。  
  
 `pdwPropFlags`  
 [out]指向向属性应用任何属性标记的指针。 此值是从一个位掩码[CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)枚举。  
  
 `ppvSig`  
 [out]指向该属性的元数据签名的指针。  
  
 `pbSig`  
 [out]在返回的字节数`ppvSig`。  
  
 `pdwCPlusTypeFlag`  
 [out]一个标志，指定的类型是属性的默认值的常数。 此值是从 CorElementType 枚举。  
  
 `ppDefaultValue`  
 [out]指向将存储此属性的默认值的字节的指针。  
  
 `pcchDefaultValue`  
 [out]在宽字符为单位的大小`ppDefaultValue`，如果`pdwCPlusTypeFlag`是 ELEMENT_TYPE_STRING; 否则，此值不相关。 在这种情况下的长度`ppDefaultValue`从指定的类型推断`pdwCPlusTypeFlag`。  
  
 `pmdSetter`  
 [out]指向在表示属性 set 访问器方法的 MethodDef 标记的指针。  
  
 `pmdGetter`  
 [out]指向在表示该属性的 get 访问器方法的 MethodDef 标记的指针。  
  
 `rmdOtherMethod`  
 [out]表示与属性关联的其他方法的 MethodDef 标记的数组。  
  
 `cMax`  
 [in] `rmdOtherMethod` 数组的最大大小。 如果未提供足够大以保存所有方法的数组，它们会跳过而不发出警告。  
  
 `pcOtherMethod`  
 [out]在中返回的 MethodDef 标记数`rmdOtherMethod`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
