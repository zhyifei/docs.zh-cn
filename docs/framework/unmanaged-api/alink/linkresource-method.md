---
title: LinkResource 方法
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: 9e91d990a8f23335248043c59eb210e8c4155e3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445627"
---
# <a name="linkresource-method"></a>LinkResource 方法
资源中的链接。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 程序集的 ID。  
  
 `pszFileName`  
 文件的名称。  
  
 `pszNewLocation`  
 可选的新文件名。 如果非 NULL，`pszFileName` 将复制到 pszNewLocation。  
  
 `pszResourceName`  
 资源的名称。  
  
 `dwFlags`  
 辅助功能标志，如 `mrPublic` 和 `mrPrivate`。 此参数可传递给[DefineManifestResource 方法](../metadata/imetadataassemblyemit-definemanifestresource-method.md)。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink。  
  
## <a name="see-also"></a>另请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
