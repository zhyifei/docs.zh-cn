---
title: EmbedResource 方法
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
ms.openlocfilehash: 24279870e7406de649df56e8aad31252513e95c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446535"
---
# <a name="embedresource-method"></a>EmbedResource 方法
Declares an embedded resource. This method does not actually embed the resource.  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 ID of the assembly.  
  
 `FileToken`  
 File token or assembly ID of file that contains the resource.  
  
 `pszResourceName`  
 资源的名称。  
  
 `dwOffset`  
 Offset of resource from RVA.  
  
 `dwFlags`  
 Accessibility flags such as `mrPublic` and `mrPrivate`. These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
## <a name="return-value"></a>返回值  
 Returns S_OK if the method succeeds.  
  
## <a name="requirements"></a>要求  
 Requires alink.h.  
  
## <a name="see-also"></a>请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
