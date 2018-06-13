---
title: ImportFile 方法
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54b0a02af7f22e775e3f9567de79664c9805b4e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400645"
---
# <a name="importfile-method"></a>ImportFile 方法
导入程序集和未绑定的模块。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>参数  
 `pszFilename`  
 要导入文件的完全限定的名称。  
  
 `pszTargetName`  
 可用于重命名该文件并将其链接到程序集的可选的输出文件名称。  
  
 `fSmartImport`  
 如果为 TRUE，则使用 ImportTypes，必须手动执行否则导入。  
  
 `pImportToken`  
 若要令牌将在其中存储唯一的文件 ID 的指针。 文件可以是程序集或文件。  
  
 `ppAssemblyScope`  
 接收指向[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)。 如果文件不是程序集，可以为 NULL。  
  
 `pdwCountOfScopes`  
 指向的文件和/或已导入的作用域的计数。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h  
  
## <a name="see-also"></a>请参阅  
 [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
