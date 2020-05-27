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
ms.openlocfilehash: a18583ce807ffa672811f3a0cd1e744233f6eb30
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008818"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout 方法
完成先前对[DefineTypeDef 方法](imetadataemit-definetypedef-method.md)的调用所定义的类的字段布局。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a>参数  
 `td`  
 中一个 `mdTypeDef` 标记，该标记指定要布局的类。  
  
 `dwPackSize`  
 中封装大小为1、2、4、8或16字节。 包装大小是相邻字段之间的字节数。  
  
 `rFieldOffsets`  
 中[COR_FIELD_OFFSET](cor-field-offset-structure.md)结构的数组，其中每个结构都指定了类的字段和字段在类中的偏移量。 用终止数组 `mdTokenNil` 。  
  
 `ulClassSize`  
 中类的大小（以字节为单位）。  
  
## <a name="remarks"></a>备注  
 该类最初是通过以下方式定义的：调用[IMetaDataEmit：:D efinetypedef](imetadataemit-definetypedef-method.md)方法，并为类的字段指定三种布局之一：自动、顺序或显式。 通常，您将使用自动布局，并让运行时选择对字段进行布局的最佳方式。  
  
 不过，您可能希望根据非托管代码使用的排列方式来排列字段。 在这种情况下，请选择 "顺序" 或 "显式布局" 并调用 `SetClassLayout` 来完成字段的布局：  
  
- 顺序布局：指定包装大小。 字段根据其自然大小或包装大小对齐，以较小的字段偏移量为准。 将 `rFieldOffsets` 和设置 `ulClassSize` 为零。  
  
- 显式布局：指定每个字段的偏移量，或指定类大小和包装大小。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit 接口](imetadataemit-interface.md)
- [IMetaDataEmit2 接口](imetadataemit2-interface.md)
