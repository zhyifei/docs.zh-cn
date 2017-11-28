---
title: "ImportFileEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportFileEx
api_location: alink.dll
api_type: COM
f1_keywords: ImportFileEx
helpviewer_keywords: ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71a7bc1ba9f23f1c581ca3528752e04003d9857c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="importfileex-method"></a>ImportFileEx 方法
导入指定的程序集或未绑定的模块。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>参数  
 `pszFilename`  
 要从中导入的文件的完全限定的名称。  
  
 `pszTargetName`  
 目标文件的可选名称。  
  
 `fSmartImport`  
 如果为 TRUE，则使用 ImportTypes，必须手动执行否则导入。  
  
 `dwOpenFlags`  
 要传递到标志[OpenScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)。  
  
 `pImportToken`  
 接收要导入的文件 ID。  
  
 `ppAssemblyScope`  
 接收程序集导入作用域[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口。 如果文件不是程序集，是设置为 NULL。  
  
 `pdwCountOfScopes`  
 接收的导入的文件和/或作用域的数量。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h。  
  
## <a name="see-also"></a>另请参阅  
 [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
