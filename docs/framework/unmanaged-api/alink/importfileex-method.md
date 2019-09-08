---
title: ImportFileEx 方法
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777113"
---
# <a name="importfileex-method"></a>ImportFileEx 方法
导入指定的程序集或未绑定模块。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>参数  
 `pszFilename`  
 要导入的文件的完全限定名称。  
  
 `pszTargetName`  
 目标文件的可选名称。  
  
 `fSmartImport`  
 如果为 TRUE，则使用 ImportTypes，否则必须手动执行导入。  
  
 `dwOpenFlags`  
 要传递给[OpenScope 方法](../metadata/imetadatadispenser-openscope-method.md)的标志。  
  
 `pImportToken`  
 接收正在导入的文件的 ID。  
  
 `ppAssemblyScope`  
 接收程序集导入范围[IMetaDataAssemblyImport 接口](../metadata/imetadataassemblyimport-interface.md)接口。 如果文件不是程序集，则设置为 NULL。  
  
 `pdwCountOfScopes`  
 接收导入文件和/或范围的计数。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink。  
  
## <a name="see-also"></a>请参阅

- [IALink2 接口](ialink2-interface.md)
- [IALink 接口](ialink-interface.md)
- [ALink API](index.md)
