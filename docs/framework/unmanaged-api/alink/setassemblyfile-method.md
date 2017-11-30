---
title: "SetAssemblyFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetAssemblyFile
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyFile
helpviewer_keywords: SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d83062db41b5fa1485555de40be0a39a65e0459a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="setassemblyfile-method"></a>SetAssemblyFile 方法
指定要生成的程序集的名称。 不是针对使用时生成未绑定的模块。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a>参数  
 `pszFilename`  
 清单文件的完全限定的名称。  
  
 `pEmitter`  
 指向[IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口。  
  
 `afFlags`  
 标记中定义[AssemblyFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)。  
  
 `pAssemblyID`  
 指向生成的程序集的 ID。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h。  
  
## <a name="see-also"></a>另请参阅  
 [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
