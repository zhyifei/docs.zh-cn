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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e22cf8e540bfdb53ad243640dac110b5750e53e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout 方法
完成已由调用定义的类的字段的布局[DefineTypeDef 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a>参数  
 `td`  
 [in]`mdTypeDef`标记，用于指定要进行布局的类。  
  
 `dwPackSize`  
 [in]包装大小： 1、 2、 4、 8 或 16 字节。 封装大小为相邻字段之间的字节数。  
  
 `rFieldOffsets`  
 [in]数组[COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)结构，其中每个指定类的字段和字段的偏移量在类中。 终止与数组`mdTokenNil`。  
  
 `ulClassSize`  
 [in]以字节为单位，类的大小。  
  
## <a name="remarks"></a>备注  
 通过调用最初定义类[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)方法，并指定三种布局的类的字段之一： 自动、 顺序，或显式。 通常情况下，将使用自动布局，并让运行时选择字段的布局的最佳方式。  
  
 但是，你可能想根据非托管代码使用的排列方式进行布局的字段。 在这种情况下，选择连续或显式布局，并调用`SetClassLayout`完成字段的布局：  
  
-   顺序布局： 指定的包装大小。 根据其原始大小或包装大小，无论结果的较小的偏移量的字段对齐字段。 设置`rFieldOffsets`和`ulClassSize`为零。  
  
-   显式布局： 指定每个字段的偏移量，或者指定类大小和封装大小。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
