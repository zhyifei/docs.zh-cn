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
ms.openlocfilehash: 44f97ef498eb8e64c55fc86b9f290b9e088293f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432067"
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
  
## <a name="parameters"></a>参数  
 `szName`  
 中要导出的类型的名称。 对于公共语言运行时版本1.1，导出类型的名称必须与在该类型的 `TypeDef` 中指定的名称完全匹配。  
  
 `tkImplementation`  
 中指定在何处实现导出类型的标记。 有效值及其关联的含义如下：  
  
- `mdFile` 类型在此程序集内的其他文件中实现。  
  
- `mdAssemblyRef` 类型是在不同的程序集中实现的。  
  
- `mdExportedTYpe` 类型嵌套在某个其他类型中。  
  
- `mdFileNil` 类型与清单位于同一文件中，并且不是嵌套类型。  
  
 `tkTypeDef`  
 中用于指定要导出的类型的元数据的令牌。 此值输入在实现类型的文件中的 `TypeDef` 表中，并且仅当该文件在此程序集中时才适用。  
  
 `dwExportedTypeFlags`  
 中[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)枚举值的按位组合，用于定义导出的类型的属性设置。  
  
 `pmdct`  
 弄指向返回的元数据标记的指针，该标记指示导出的类型。  
  
## <a name="remarks"></a>备注  
 必须为此程序集公开的每个类型定义 `ExportedType` 的元数据结构，该结构在包含清单的模块中实现。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
