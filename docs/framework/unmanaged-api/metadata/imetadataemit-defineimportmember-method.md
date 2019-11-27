---
title: IMetaDataEmit::DefineImportMember 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: 75711b3d87699ff5db21a04351ff0acaccabb5aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431859"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember 方法
创建对在当前范围外定义的类型或模块的指定成员的引用，并定义该引用的标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DefineImportMember (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,   
    [in]  mdToken                  mbMember,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [in]  mdToken                  tkParent,   
    [out] mdMemberRef              *pmr   
);  
```  
  
## <a name="parameters"></a>参数  
 `pAssemImport`  
 中一个[IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口，它表示从中导入目标成员的程序集。  
  
 `pbHashValue`  
 中一个数组，包含 `pAssemImport`指定的程序集的哈希。  
  
 `cbHashValue`  
 [in] `pbHashValue` 数组中的字节数。  
  
 `pImport`  
 中一个[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口，表示从其导入目标成员的元数据范围。  
  
 `mbMember`  
 中指定目标成员的元数据标记。 标记可以是 `mdMethodDef` （对于成员方法）、`mdProperty` （对于成员属性）或 `mdFieldDef` （对于成员字段）标记。  
  
 `pAssemEmit`  
 中一个[IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)接口，该接口表示向其中导入目标成员的程序集。  
  
 `tkParent`  
 中类型或模块的 `mdTypeRef` 或 `mdModuleRef` 标记，分别拥有目标成员。  
  
 `pmr`  
 弄在成员引用的当前范围内定义 `mdMemberRef` 标记。  
  
## <a name="remarks"></a>备注  
 `DefineImportMember` 方法查找由 `mbMember`指定、由 `pImport`指定的另一个作用域中定义的成员，并检索其属性。 它使用此信息调用当前范围中的[IMetaDataEmit：:D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)方法来创建成员引用。  
  
 通常，在使用 `DefineImportMember` 方法之前，必须在当前作用域内为目标成员的父类、接口或模块创建类型引用或模块引用。 然后，在 `tkParent` 参数中传递此引用的元数据标记。 如果目标成员的父成员稍后将由编译器或链接器解析，则不需要创建对它的引用。 概况如下：  
  
- 如果目标成员是字段或方法，则使用[IMetaDataEmit：:D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)或[IMetaDataEmit：:D efineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)方法为成员的父类或父接口创建类型引用（在当前范围内）。  
  
- 如果目标成员是全局变量或全局函数（即不是类或接口的成员），请使用[IMetaDataEmit：:D efinemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)方法为成员的父模块创建一个模块引用（在当前范围内）。  
  
- 如果在以后通过编译器或链接器解析目标成员的父成员，则将 `mdTokenNil` 传递 `tkParent`。 这种情况的唯一应用场景是从一个 .obj 文件中导入全局函数或全局变量，该文件最终将链接到当前模块和合并的元数据中。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
