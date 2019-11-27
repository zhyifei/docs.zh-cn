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
ms.openlocfilehash: 031996813718a074eebab62ff54a2de52b898c22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450213"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef 方法
创建公共语言运行时类型的类型定义，并获取该类型定义的元数据标记。  
  
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
  
## <a name="parameters"></a>参数  
 `szTypeDef`  
 中Unicode 中类型的名称。  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` 特性。 这是 `CoreTypeAttr` 值的位掩码。  
  
 `tkExtends`  
 中基类的标记。 它必须是 `mdTypeDef` 或 `mdTypeRef` 令牌。  
  
 `rtkImplements`  
 中标记的数组，该数组指定此类或接口实现的接口。  
  
 `ptd`  
 弄分配 `mdTypeDef` 标记。  
  
## <a name="remarks"></a>备注  
 `dwTypeDefFlags` 中的标志指定正在创建的类型是通用类型系统引用类型（类或接口）还是通用类型系统值类型。  
  
 根据提供的参数，此方法也可以为此类型继承或实现的每个接口创建 `mdInterfaceImpl` 记录。 但是，此方法不会返回这些 `mdInterfaceImpl` 标记中的任何一个。 如果客户端想要稍后添加或修改 `mdInterfaceImpl` 令牌，则必须使用 `IMetaDataImport` 接口对其进行枚举。 如果要使用 `[default]` 接口的 COM 语义，应提供默认接口作为 `rtkImplements`中的第一个元素;在类上设置的自定义属性将指示类具有默认接口（始终假定为为类声明的第一个 `mdInterfaceImpl` 标记）。  
  
 `rtkImplements` 数组的每个元素都包含一个 `mdTypeDef` 或 `mdTypeRef` 标记。 数组中的最后一个元素必须是 `mdTokenNil`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
