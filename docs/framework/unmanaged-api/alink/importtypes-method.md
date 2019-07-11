---
title: ImportTypes 方法
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9876e3ba5ea67442714c2d00b1901c25e54494f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741634"
---
# <a name="importtypes-method"></a>ImportTypes 方法
启动导入的类型从通过导入每个作用域[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 要导入到的程序集的 ID。  
  
 `FileToken`  
 若要从导入的文件的 ID。  
  
 `dwScope`  
 要导入的从零开始范围。  
  
 `phEnum`  
 在此作用域中接收的类型的枚举器句柄。  
  
 `ppImportScope`  
 可选择性地接收[IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口。  
  
 `pdwCountOfTypes`  
 可选择性地指示作用域中接收的类型的计数。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h  
  
## <a name="see-also"></a>请参阅

- [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
