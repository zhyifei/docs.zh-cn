---
title: IMetaDataTables::GetRow 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177105"
---
# <a name="imetadatatablesgetrow-method"></a>IMetaDataTables::GetRow 方法
在指定的表索引的表中获取指定行索引处的行。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a>parameters  
 `ixTbl`  
 [在]将从中检索行的表的索引。  
  
 `rid`  
 [在]要获取的行的索引。  
  
 `ppRow`  
 [出]指向行的指针。  
  
## <a name="remarks"></a>备注  

  我们不建议使用此方法，因为它不返回一致的结果。 有关 GUID 表的信息，请参阅通用语言基础结构 （CLI） 文档，尤其是"分区 II：元数据定义和语义"。 文档可在线获取;请参阅[ECMA C# 和通用语言基础结构标准和](../../../standard/components.md#applicable-standards)[标准 ECMA-335 - 通用语言基础结构 （CLI）。](http://www.ecma-international.org/publications/standards/Ecma-335.htm)  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataTables 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
