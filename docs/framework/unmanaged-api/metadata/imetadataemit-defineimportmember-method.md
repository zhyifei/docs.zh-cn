---
title: "IMetaDataEmit::DefineImportMember 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1bbe2c3144372ba66a0b3bad6198aefeeb7e12d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember 方法
创建到的指定成员的类型或模块，它定义出当前范围，并定义该引用的令牌的引用。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `pAssemImport`  
 [in][IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)表示从中导入目标成员的程序集的接口。  
  
 `pbHashValue`  
 [in]数组包含指定的程序集哈希`pAssemImport`。  
  
 `cbHashValue`  
 [in] `pbHashValue` 数组中的字节数。  
  
 `pImport`  
 [in][IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)表示从中导入目标成员的元数据范围的接口。  
  
 `mbMember`  
 [in]指定的目标成员元数据标记。 令牌可以`mdMethodDef`（对于成员方法）， `mdProperty` （对于成员属性），或`mdFieldDef`（适用于的成员字段中） 令牌。  
  
 `pAssemEmit`  
 [in][IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)表示目标成员导入的程序集的接口。  
  
 `tkParent`  
 [in]`mdTypeRef`或`mdModuleRef`标记为类型或模块，分别拥有目标成员。  
  
 `pmr`  
 [out]`mdMemberRef`在成员引用的当前作用域中定义的令牌。  
  
## <a name="remarks"></a>备注  
 `DefineImportMember`方法查找由指定的成员`mbMember`，即在另一个作用域中定义由指定`pImport`，并检索其属性。 它将使用此信息来调用[imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)在当前范围内创建的成员引用的方法。  
  
 通常情况下，在你使用`DefineImportMember`方法中，你必须创建，在当前作用域、 类型引用或目标成员的父类、 接口或模块的模块参考。 然后传入此引用的元数据标记`tkParent`自变量。 不需要创建对目标成员的父级的引用，如果它将解决更高版本的编译器或链接器。 总结：  
  
-   如果目标成员为字段或方法，可以使用两种[imetadataemit:: Definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)或[imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)方法为创建的类型引用，在当前范围内，成员的父类或父接口。  
  
-   如果目标成员全局变量或全局函数 （即，不是成员的类或接口），请使用[imetadataemit:: Definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)方法在当前范围中，为成员的父代中创建的模块引用，模块。  
  
-   如果目标成员的父级将解决更高版本的编译器或链接器，则传递`mdTokenNil`中`tkParent`。 这适用的唯一情形时，可以全局函数或全局变量从最终将链接到当前模块的.obj 文件导入和合并的元数据。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
