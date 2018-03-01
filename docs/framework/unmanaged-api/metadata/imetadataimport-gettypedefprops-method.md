---
title: "IMetaDataImport::GetTypeDefProps 方法"
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
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f3e7f2c2fe602ef3464766b62ef12e8f83767bf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgettypedefprops-method"></a>IMetaDataImport::GetTypeDefProps 方法
返回元数据信息<xref:System.Type>由指定的 TypeDef 标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
#### <a name="parameters"></a>参数  
 `td`  
 [in]表示要返回的元数据的类型的 TypeDef 标记。  
  
 `szTypeDef`  
 [out]包含的类型名称的缓冲区。  
  
 `cchTypeDef`  
 [in]在宽字符为单位的大小`szTypeDef`。  
  
 `pchTypeDef`  
 [out]在中返回的宽字符数`szTypeDef`。  
  
 `pdwTypeDefFlags`  
 [out]指向任何修改的类型定义的标志的指针。 此值是从一个位掩码[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)枚举。  
  
 `ptkExtends`  
 [out]TypeDef 或 TypeRef 元数据标记，用于表示所请求类型的基类型。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
