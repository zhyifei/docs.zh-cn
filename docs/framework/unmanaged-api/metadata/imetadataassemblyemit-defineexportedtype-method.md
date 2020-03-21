---
title: IMetaDataAssemblyEmit::DefineExportedType 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177884"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType 方法
创建包含指定导出类型的元数据的 `ExportedType` 结构，并返回关联的元数据标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a>parameters  
 `szName`  
 [在]要导出的类型的名称。 对于通用语言运行时的版本 1.1，导出类型的名称必须与 类型中`TypeDef`给出的名称完全匹配。  
  
 `tkImplementation`  
 [在]指定导出类型的实现位置的令牌。 有效值及其相关含义包括：  
  
- `mdFile`该类型在此程序集中的其他文件中实现。  
  
- `mdAssemblyRef`该类型在不同的程序集中实现。  
  
- `mdExportedTYpe`类型嵌套在某种其他类型中。  
  
- `mdFileNil`类型与清单位于同一文件中，不是嵌套类型。  
  
 `tkTypeDef`  
 [在]指定要导出的类型的元数据的令牌。 此值在文件中实现该类型的`TypeDef`表中输入，并且仅当该文件位于此程序集中时才相关。  
  
 `dwExportedTypeFlags`  
 [在][CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)枚举值的位组合，用于定义导出类型的属性设置。  
  
 `pmdct`  
 [出]指向返回的元数据令牌的指针，指示导出的类型。  
  
## <a name="remarks"></a>备注  
 必须`ExportedType`为此程序集公开的并且在包含清单的模块以外的模块中实现的每一种类型定义元数据结构。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
