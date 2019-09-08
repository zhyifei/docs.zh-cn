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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 763b7a776007c2ce8dac42c6a5f7f00f6eb58a10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776955"
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
 可选的新文件名。 如果非 NULL， `pszFileName`则将复制到 pszNewLocation。  
  
 `pszResourceName`  
 资源的名称。  
  
 `dwFlags`  
 辅助功能标志`mrPublic` ，例如`mrPrivate`和。 此参数可传递给[DefineManifestResource 方法](../metadata/imetadataassemblyemit-definemanifestresource-method.md)。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink。  
  
## <a name="see-also"></a>请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
