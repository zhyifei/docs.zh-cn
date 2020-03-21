---
title: IMetaDataEmit::SetClassLayout 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177564"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout 方法
完成由之前调用[DefineTypeDef 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)定义的类的字段布局。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a>parameters  
 `td`  
 [在]指定`mdTypeDef`要布局的类的令牌。  
  
 `dwPackSize`  
 [在]包装尺寸：1、2、4、8 或 16 字节。 包装大小是相邻字段之间的字节数。  
  
 `rFieldOffsets`  
 [在][COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)结构数组，每个结构指定类的字段和类中的字段偏移量。 使用 终止数组`mdTokenNil`。  
  
 `ulClassSize`  
 [在]类的大小（以字节为单位）。  
  
## <a name="remarks"></a>备注  
 类最初通过调用[IMetaDataEmit：:DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)方法来定义，并为类的字段指定三个布局之一：自动、顺序或显式。 通常，您将使用自动布局，让运行时选择布局字段的最佳方式。  
  
 但是，您可能希望根据非托管代码使用的排列方式布局字段。 在这种情况下，选择顺序或显式布局并调用`SetClassLayout`以完成字段的布局：  
  
- 顺序布局：指定包装大小。 字段根据其自然大小或包装大小对齐，以导致字段偏移较小的为准。 设置`rFieldOffsets`和`ulClassSize`零。  
  
- 显式布局：指定每个字段的偏移量或指定类大小和包装大小。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
