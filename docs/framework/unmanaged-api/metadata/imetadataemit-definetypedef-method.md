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
ms.openlocfilehash: dc064b00e32bb6b1d8c2d0c20f571b35919eae23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009335"
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
 [in] `TypeDef`属性. 这是一个值的位掩码 `CoreTypeAttr` 。  
  
 `tkExtends`  
 中基类的标记。 它必须是 `mdTypeDef` 或 `mdTypeRef` 令牌。  
  
 `rtkImplements`  
 中标记的数组，该数组指定此类或接口实现的接口。  
  
 `ptd`  
 弄`mdTypeDef`分配的令牌。  
  
## <a name="remarks"></a>备注  
 中的标志 `dwTypeDefFlags` 指定正在创建的类型是否为通用类型系统引用类型（类或接口）或通用类型系统值类型。  
  
 根据提供的参数，此方法也可以为 `mdInterfaceImpl` 此类型继承或实现的每个接口创建一条记录。 但是，此方法不会返回这些标记中的任何一个 `mdInterfaceImpl` 。 如果客户端想要以后添加或修改 `mdInterfaceImpl` 令牌，则必须使用 `IMetaDataImport` 接口对其进行枚举。 如果要使用接口的 COM 语义 `[default]` ，则应该提供默认接口作为中的第一个元素 `rtkImplements` ; 在类上设置的自定义属性将指示类具有默认接口（始终假定为 `mdInterfaceImpl` 为类声明的第一个标记）。  
  
 数组的每个元素都 `rtkImplements` 包含一个 `mdTypeDef` 或 `mdTypeRef` 标记。 数组中的最后一个元素必须是 `mdTokenNil` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit 接口](imetadataemit-interface.md)
- [IMetaDataEmit2 接口](imetadataemit2-interface.md)
