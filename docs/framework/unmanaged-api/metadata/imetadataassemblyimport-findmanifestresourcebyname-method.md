---
title: "IMetaDataAssemblyImport::FindManifestResourceByName 方法"
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
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d6cc738c227157b45e242fb46a672d28d6ce778
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a>IMetaDataAssemblyImport::FindManifestResourceByName 方法
获取具有指定名称的清单资源的指针。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a>参数  
 `szName`  
 [in]资源的名称。  
  
 `ptkManifestResource`  
 [out]用于存储数组`mdManifestResource`元数据标记，其中每个表示清单资源。  
  
## <a name="remarks"></a>备注  
 `FindManifestResourceByName`方法使用由解析的引用的公共语言运行时的标准规则。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [运行时如何定位程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
