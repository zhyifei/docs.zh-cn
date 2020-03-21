---
title: IMetaDataEmit::DefineTypeDef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175754"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef 方法
为通用语言运行时类型创建类型定义，并获取该类型定义的元数据令牌。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>parameters  
 `szTypeDef`  
 [在]Unicode 中类型的名称。  
  
 `dwTypeDefFlags`  
 [在]`TypeDef`属性。 这是值的`CoreTypeAttr`位掩码。  
  
 `tkExtends`  
 [在]基类的令牌。 它必须是 或`mdTypeDef``mdTypeRef`标记。  
  
 `rtkImplements`  
 [在]指定此类或接口实现的接口的令牌数组。  
  
 `ptd`  
 [出]分配的`mdTypeDef`令牌。  
  
## <a name="remarks"></a>备注  
 中`dwTypeDefFlags`的标志指定正在创建的类型是公共类型系统引用类型（类或接口）还是公共类型系统值类型。  
  
 根据提供的参数，此方法作为副作用，还可以为此类型继承或实现的每个接口创建`mdInterfaceImpl`记录。 但是，此方法不会返回任何这些`mdInterfaceImpl`令牌。 如果客户端希望以后添加或修改`mdInterfaceImpl`令牌，则必须使用接口`IMetaDataImport`枚举它们。 如果要使用接口的`[default]`COM 语义，则应将默认接口作为`rtkImplements`中的第一个元素提供 。类上的自定义属性集将指示类具有默认接口（始终假定该接口是为类声明的第一个`mdInterfaceImpl`令牌）。  
  
 `rtkImplements`数组的每个元素都包含 或`mdTypeDef``mdTypeRef`令牌。 数组中的最后一个元素必须为`mdTokenNil`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
