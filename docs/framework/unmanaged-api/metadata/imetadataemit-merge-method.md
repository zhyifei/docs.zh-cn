---
title: IMetaDataEmit::Merge 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: 759358822ed865c89f6f55084d1e7f6143506e93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175702"
---
# <a name="imetadataemitmerge-method"></a>IMetaDataEmit::Merge 方法
将指定的导入作用域添加到要合并的范围列表中。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a>parameters  
 `pImport`  
 [在]指向[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)对象的指针，用于标识要合并的导入作用域。  
  
 `pIMap`  
 [在]指向[IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)对象的指针，用于指定令牌重新映射。  
  
 `pHandler`  
 [在]指向指定错误的[IUnknown](/cpp/atl/iunknown)对象的指针。  
  
## <a name="remarks"></a>备注  
 调用[IMetaDataEmit：：合并结束](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)以触发将元数据合并到单个作用域中。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
