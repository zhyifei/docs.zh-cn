---
title: ImportTypes2 方法
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce09eca30e1edb9e1afc02216a07955a5fed4fd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787257"
---
# <a name="importtypes2-method"></a>ImportTypes2 方法
启动类型的导入。 调用此方法以开始从通过[ImportFile 方法](importfile-method.md)导入的每个范围导入类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 要导入的程序集的 ID。  
  
 `FileToken`  
 要从其导入的文件的 ID。  
  
 `dwScope`  
 要从中导入的从零开始的作用域。  
  
 `phEnum`  
 接收给定范围内的类型的枚举器句柄。  
  
 `ppImportScope`  
 可以选择接收[IMetaDataImport2 接口](../metadata/imetadataimport2-interface.md)接口。  
  
 `pdwCountOfTypes`  
 可以选择接收指定范围内的类型的计数。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink  
  
## <a name="see-also"></a>请参阅

- [IALink2 接口](ialink2-interface.md)
- [IALink 接口](ialink-interface.md)
- [ALink API](index.md)
