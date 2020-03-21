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
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175858"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember 方法
创建对在当前作用域之外定义的类型或模块的指定成员的引用，并为该引用定义令牌。  
  
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
  
## <a name="parameters"></a>parameters  
 `pAssemImport`  
 [在][IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)，表示从中导入目标成员的程序集。  
  
 `pbHashValue`  
 [在]包含 的数组，其中包含 由 指定的`pAssemImport`程序集的哈希值。  
  
 `cbHashValue`  
 [in] `pbHashValue` 数组中的字节数。  
  
 `pImport`  
 [在][IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口，表示从中导入目标成员的元数据范围。  
  
 `mbMember`  
 [在]指定目标成员的元数据令牌。 令牌可以是`mdMethodDef`（对于成员方法）、（`mdProperty`对于成员属性）或`mdFieldDef`（对于成员字段）的令牌。  
  
 `pAssemEmit`  
 [在][IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)接口，表示将目标成员导入到的程序集。  
  
 `tkParent`  
 [在]分别`mdTypeRef`拥有`mdModuleRef`目标成员的类型或模块的 或 令牌。  
  
 `pmr`  
 [出]在`mdMemberRef`成员引用的当前作用域中定义的令牌。  
  
## <a name="remarks"></a>备注  
 方法`DefineImportMember`查找由`mbMember`指定的成员，该成员在由 指定的另一个作用域中定义`pImport`，由 指定并检索其属性。 它使用此信息调用当前作用域中的[IMetaDataEmit：:Define会员Ref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)方法来创建成员引用。  
  
 通常，在使用`DefineImportMember`方法之前，必须在当前作用域中为目标成员的父类、接口或模块创建类型引用或模块引用。 然后，在参数中传递此引用的`tkParent`元数据令牌。 如果编译器或链接器稍后将解析目标成员的父项，则无需创建对目标成员的父项的引用。 总结：  
  
- 如果目标成员是字段或方法，请使用[IMetaDataEmit：:DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)或[IMetaDataEmit：:DefineImportType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)，为成员的父类或父接口在当前作用域中创建类型引用。  
  
- 如果目标成员是全局变量或全局函数（即不是类或接口的成员），请使用[IMetaDataEmit：:DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)方法为成员的父模块在当前作用域中创建模块引用。  
  
- 如果稍后编译器或链接器将解析目标成员的父成员的父级，则将传递`mdTokenNil``tkParent`。 唯一适用这种情况的情况是，全局函数或全局变量从 .obj 文件导入，该文件最终将链接到当前模块并合并元数据。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
