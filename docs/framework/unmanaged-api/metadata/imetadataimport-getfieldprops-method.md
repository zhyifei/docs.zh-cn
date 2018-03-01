---
title: "IMetaDataImport::GetFieldProps 方法"
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
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7785ea6beaa882e72d200ef559ba75538224091d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetfieldprops-method"></a>IMetaDataImport::GetFieldProps 方法
获取与指定 FieldDef 标记引用的字段关联的元数据。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `mb`  
 [in]表示要获取关联的元数据的字段的 FieldDef 标记。  
  
 `pClass`  
 [out]指向表示字段所属的类类型的 TypeDef 标记的指针。  
  
 `szField`  
 [out]字段的名称。  
  
 `cchField`  
 [in]在宽字符的缓冲区的大小*szField*。  
  
 `pchField`  
 [out]返回缓冲区的实际大小。  
  
 `pdwAttr`  
 [out]字段的元数据与关联的标志。  
  
 `ppvSigBlob`  
 [in]指向描述字段的二进制元数据值的指针。  
  
 `pcbSigBlob`  
 [out]以字节为单位的大小`ppvSigBlob`。  
  
 `pdwCPlusTypeFlag`  
 [out]用于指定该字段的值类型的标志。  
  
 `ppValue`  
 [out]字段的常量值。  
  
 `pcchValue`  
 [out]以字符为单位的大小`ppValue`，或如果不存在任何字符串则为零。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
