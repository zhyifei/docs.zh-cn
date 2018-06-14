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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d93763da2afbbdb1e738c802ba172e9f16e5f7af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448453"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps 方法
获取元数据信息，包括名称、 二进制签名和相对虚拟地址的<xref:System.Type>指定的元数据标记所引用的成员。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `mb`  
 [in]标记，用于引用要获取有关关联的元数据的成员。  
  
 `pClass`  
 [out]指向表示的成员的类的元数据标记的指针。  
  
 `szMember`  
 [out]成员的名称。  
  
 `cchMember`  
 [in]在宽字符为单位的大小`szMember`缓冲区。  
  
 `pchMember`  
 [out]以宽字符为单位返回的名称的大小。  
  
 `pdwAttr`  
 [out]应用于的成员的任何标志值。  
  
 `ppvSigBlob`  
 [out]指向成员的二进制元数据签名的指针。  
  
 `pcbSigBlob`  
 [out]以字节为单位的大小`ppvSigBlob`。  
  
 `pulCodeRVA`  
 [out]指向成员的相对虚拟地址的指针。  
  
 `pdwImplFlags`  
 [out]成员关联的任何方法实现标志。  
  
 `pdwCPlusTypeFlag`  
 [out]用于将标记的标志<xref:System.ValueType>。  
  
 `ppValue`  
 [out]返回此成员的常量字符串值。  
  
 `pcchValue`  
 [out]以字符为单位的大小`ppValue`，或为零`ppValue`不包含一个字符串。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
