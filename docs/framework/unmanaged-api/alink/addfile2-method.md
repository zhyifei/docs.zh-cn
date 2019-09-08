---
title: AddFile2 方法
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3a6892dbed172c0be3b036014d393657dbc8593
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777524"
---
# <a name="addfile2-method"></a>AddFile2 方法
将文件添加到程序集。 还可用于创建未绑定的模块。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 向其中添加文件的程序集的 ID。  
  
 `pszFilename`  
 要添加的文件的名称。  
  
 `dwFlags`  
 Com `FileDef` + 标志`ffContainsNoMetaData` ，例如`ffWriteable`和。 `dwFlags`传递给[DefineFile 方法](../metadata/imetadataassemblyemit-definefile-method.md)。  
  
 `pEmitter`  
 [IMetaDataEmit2 接口](../metadata/imetadataemit2-interface.md)接口的接口。  
  
 `pFileToken`  
 接收要添加的文件的 ID。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink。  
  
## <a name="see-also"></a>请参阅

- [IALink2 接口](ialink2-interface.md)
- [IALink 接口](ialink-interface.md)
- [ALink API](index.md)
