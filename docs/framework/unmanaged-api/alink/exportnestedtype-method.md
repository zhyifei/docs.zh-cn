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
ms.openlocfilehash: 0afe4daa1c85f3e15addac55bdbe631d40e03f19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407554"
---
# <a name="exportnestedtype-method"></a>ExportNestedType 方法
为可导出指定嵌套的类型。 [ExportType 方法](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md)还可以导出嵌套类型，但此方法也越快。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `AssemblyID`  
 要从导出程序集的 ID。  
  
 `FileToken`  
 文件的标记或定义的类型，要成为可导出的文件的程序集。  
  
 `TypeToken`  
 键入要成为可导出的类型的令牌。  
  
 `ParentType`  
 父类型的令牌。  
  
 `pszTypename`  
 要导出的完全限定的类型名称。  
  
 `dwFlags`  
 `ComType` 标志，如`tdPublic`或`tdNested`。 此值可能会传递给[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。  
  
 `pType`  
 收到导出的类型的令牌。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h  
  
## <a name="see-also"></a>请参阅  
 [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
