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
ms.openlocfilehash: f19dd114925ed1fd12bcc0056411c3e3d4181215
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777094"
---
# <a name="importtypes-method"></a>ImportTypes 方法
开始从通过[ImportFile 方法](importfile-method.md)导入的每个范围导入类型。  
  
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
 要从中导入的文件的 ID。  
  
 `dwScope`  
 要导入的从零开始的范围。  
  
 `phEnum`  
 接收此范围内的类型的枚举器句柄。  
  
 `ppImportScope`  
 可以选择接收[IMetaDataImport 接口](../metadata/imetadataimport-interface.md)接口。  
  
 `pdwCountOfTypes`  
 可以选择接收指定范围内的类型的计数。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink  
  
## <a name="see-also"></a>请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
