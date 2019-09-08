---
title: ExportNestedType 方法
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 570e48788a11045882ef546bf6bc22315c2a02b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777277"
---
# <a name="exportnestedtype-method"></a>ExportNestedType 方法
指定嵌套类型为可导出。 [ExportType 方法](exporttype-method.md)还可以导出嵌套类型，但此方法的速度更快。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 要从中导出的程序集的 ID。  
  
 `FileToken`  
 定义要导出的类型的文件标记或文件的程序集。  
  
 `TypeToken`  
 要使其可导出的类型的类型标记。  
  
 `ParentType`  
 父类型的标记。  
  
 `pszTypename`  
 要导出的完全限定的类型名称。  
  
 `dwFlags`  
 `ComType`标志， `tdPublic`如或`tdNested`。 此值可传递给[DefineExportedType 方法](../metadata/imetadataassemblyemit-defineexportedtype-method.md)。  
  
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
