---
title: "IMetaDataAssemblyImport::GetFileProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetFileProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55984c4adaf291e3b962514cdc3bea964d1c91bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>IMetaDataAssemblyImport::GetFileProps 方法
获取与指定的元数据签名的文件的属性。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `mdf`  
 [in]`mdFile`表示为其获取属性的文件的元数据标记。  
  
 `szName`  
 [out]文件的简单名称。  
  
 `cchName`  
 [in]大小，以宽字符为单位的`szName`。  
  
 `pchName`  
 [out]中实际返回的宽字符数`szName`。  
  
 `ppbHashValue`  
 [out]指向哈希值的指针。 这是使用 sha-1 算法，该文件的哈希。  
  
 `pcbHashValue`  
 [out]返回的哈希值中的宽字符数。  
  
 `pdwFileFlags`  
 [out]指向描述应用于文件的元数据的标志的指针。 标志值是一个或多个组合[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)值。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
