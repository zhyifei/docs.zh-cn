---
title: "ImportTypes 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportTypes
api_location: alink.dll
api_type: COM
f1_keywords: ImportTypes
helpviewer_keywords: ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8fb83d4e3244010550cb21fedbc6c3b1c5d60d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="importtypes-method"></a>ImportTypes 方法
启动从通过导入每个作用域的类型的导入[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a>参数  
 `AssemblyID`  
 要导入到的程序集的 ID。  
  
 `FileToken`  
 要从中导入的文件 ID。  
  
 `dwScope`  
 要导入的从零开始范围。  
  
 `phEnum`  
 接收此范围中的类型的枚举器句柄。  
  
 `ppImportScope`  
 （可选） 接收[IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口。  
  
 `pdwCountOfTypes`  
 （可选） 指定范围内接收的类型的计数。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h  
  
## <a name="see-also"></a>另请参阅  
 [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
