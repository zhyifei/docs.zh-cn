---
title: AddImport 方法
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aed70a78e2513f4d63fbf8ca8868f26efbac9ae8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787666"
---
# <a name="addimport-method"></a>AddImport 方法
将导入添加到程序集。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 要扩充的程序集的唯一 ID。  
  
 `ImportToken`  
 要导入的文件从[ImportFile 方法](importfile-method.md)检索的唯一 ID。  
  
 `dwFlags`  
 Com + FileDef 标志`ffContainsNoMetaData` ，例如和。 `ffWriteable` `dwFlags`传递给[DefineFile 方法](../metadata/imetadataassemblyemit-definefile-method.md)。  
  
 `pFileToken`  
 指向接收结果文件的 ID 的标记的指针。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink  
  
## <a name="see-also"></a>请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
