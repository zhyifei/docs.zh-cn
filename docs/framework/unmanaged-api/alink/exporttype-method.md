---
title: ExportType 方法
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 455f71c5b576d1b57db591dab2a3e59f8a5eed67
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777286"
---
# <a name="exporttype-method"></a>ExportType 方法
指定类型可导出。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 要从中导出的程序集的 ID。  
  
 `FileToken`  
 定义可导出类型的文件的文件标记或程序集 ID。  
  
 `TypeToken`  
 要使其可导出的类型的标记。  
  
 `pszTypename`  
 要使其可导出的完全限定的类型名称。  
  
 `dwFlags`  
 `ComType`标志， `tdPublic`如或`tdNested`。 此参数可传递给[DefineExportedType 方法](../metadata/imetadataassemblyemit-defineexportedtype-method.md)。  
  
 `pType`  
 接收导出类型的令牌。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink  
  
## <a name="see-also"></a>请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
