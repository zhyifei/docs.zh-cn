---
title: "IMetaDataImport::GetNameFromToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNameFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baa0c0e78f7912561b432effd2bf5503e0f06ae7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetnamefromtoken-method"></a>IMetaDataImport::GetNameFromToken 方法
获取指定的元数据标记所引用的对象的 UTF-8 名称。 此方法已过时。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a>参数  
 `tk`  
 [in]表示要返回的名称的对象的标记。  
  
 `pszUtf8NamePtr`  
 [out]指向堆中的 utf-8 对象名称的指针。  
  
## <a name="remarks"></a>备注  
 `GetNameFromToken` 已过时。 作为替代方法，调用方法，以获取的令牌需要，如的特定类型的属性`GetFieldProps`字段或`GetMethodProps`方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** 1.0  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
