---
title: ImportFile2 方法
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a03fc24e5ef932d13c0d195f53c703cdd3ff45ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776939"
---
# <a name="importfile2-method"></a>ImportFile2 方法
导入程序集和未绑定模块。 此方法类似于[ImportFile 方法](importfile-method.md)，但即使磁盘上没有要导入的文件也能正常工作。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `pszFilename`  
 要导入的文件的名称。  
  
 `pszTargetName`  
 可选输出文件名，可用于在文件链接到程序集时对其进行重命名。  
  
 `pAssemblyScopeIn`  
 可选范围[IMetaDataAssemblyImport 接口](../metadata/imetadataassemblyimport-interface.md)接口。  
  
 `fSmartImport`  
 如果为 TRUE，则使用 ImportTypes，否则必须手动执行导入。  
  
 `pImportToken`  
 接收文件或程序集的 ID。  
  
 `ppAssemblyScope`  
 接收[IMetaDataAssemblyImport 接口](../metadata/imetadataassemblyimport-interface.md)接口。 如果文件不是程序集，则为 NULL。  
  
 `pdwCountOfScopes`  
 接收导入的文件和/或范围的发现。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink。  
  
## <a name="see-also"></a>请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
