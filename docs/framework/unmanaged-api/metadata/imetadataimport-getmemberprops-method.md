---
title: IMetaDataImport::GetMemberProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177234"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps 方法
获取存储在指定成员定义的元数据中的信息，包括指定元数据令牌引用<xref:System.Type>的成员的名称、二进制签名和相对虚拟地址。 这是一个简单的帮助方法：如果*mb*是一个方法Def，则调用**GetMethodProps;** 如果*mb*是 FieldDef，则调用**GetFieldProps。** 有关详细信息，请参阅这些其他方法。
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>parameters  
 `mb`  
 [在]引用成员获取关联的元数据的令牌。  
  
 `pClass`  
 [出]指向表示成员类的元数据令牌的指针。  
  
 `szMember`  
 [出]成员的名称。  
  
 `cchMember`  
 [在]`szMember`缓冲区的大小以宽字符表示。  
  
 `pchMember`  
 [出]返回名称的宽字符大小。  
  
 `pdwAttr`  
 [出]应用于成员的任何标志值。  
  
 `ppvSigBlob`  
 [出]指向成员的二进制元数据签名的指针。  
  
 `pcbSigBlob`  
 [出]的大小（以字节为单位）。 `ppvSigBlob`  
  
 `pulCodeRVA`  
 [出]指向成员的相对虚拟地址的指针。  
  
 `pdwImplFlags`  
 [出]与成员关联的任何方法实现标志。  
  
 `pdwCPlusTypeFlag`  
 [出]标记 的标志<xref:System.ValueType>。 它是`ELEMENT_TYPE_*`值之一。
  
 `ppValue`  
 [出]此成员返回的常量字符串值。  
  
 `pcchValue`  
 [出]如果`ppValue`不保存字符串，`ppValue`则以 字符或零表示的大小。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
