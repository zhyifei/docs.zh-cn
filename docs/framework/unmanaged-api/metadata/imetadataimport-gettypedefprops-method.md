---
title: IMetaDataImport::GetTypeDefProps 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12adffbfeb2ce6271774cf44c1a913d7a1414ba4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718606"
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
 [out]包含类型名称的缓冲区。  
  
 `cchTypeDef`  
 [in]在宽字符为单位的大小`szTypeDef`。  
  
 `pchTypeDef`  
 [out]在中返回的宽字符数`szTypeDef`。  
  
 `pdwTypeDefFlags`  
 [out]一个指向任何修改的类型定义的标志。 此值是从一个位掩码[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)枚举。  
  
 `ptkExtends`  
 [out]TypeDef 或 TypeRef 元数据标记，表示所请求类型的基类型。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 包含为 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
