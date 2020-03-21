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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179418"
---
# <a name="exportnestedtype-method"></a>ExportNestedType 方法
将嵌套类型指定为可导出类型。 [导出类型方法](exporttype-method.md)还可以导出嵌套类型，但此方法更快。  
  
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
  
## <a name="parameters"></a>parameters  
 `AssemblyID`  
 要导出的程序集的 ID。  
  
 `FileToken`  
 文件令牌或文件程序集，用于定义要导出的类型。  
  
 `TypeToken`  
 类型令牌，使可导出。  
  
 `ParentType`  
 父类型的令牌。  
  
 `pszTypename`  
 要导出的完全限定类型名称。  
  
 `dwFlags`  
 `ComType`标志，如`tdPublic``tdNested`或 。 此值可以传递给[定义导出类型方法](../metadata/imetadataassemblyemit-defineexportedtype-method.md)。  
  
 `pType`  
 接收导出类型的令牌。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则返回S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h  
  
## <a name="see-also"></a>另请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
