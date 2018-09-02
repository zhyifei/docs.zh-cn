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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d24dbcbdd8b0ed0736f7b59564cf72dffaa5a8f8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463947"
---
# <a name="imetadatatablesgetrow-method"></a>IMetaDataTables::GetRow 方法
获取指定的行索引处，在指定的表索引的表中的行。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ixTbl`  
 [in]将从其检索行的表的索引。  
  
 `rid`  
 [in]若要获取的行的索引。  
  
 `ppRow`  
 [out]指向行的指针指向的指针。  
  
## <a name="remarks"></a>备注  
 不建议使用此方法，因为它不会返回一致的结果。 GUID 表有关的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是"分区 II:: 元数据定义和语义"。 可联机获取该文档；请参阅 MSDN 上的 [ECMA C# 和公共语言基础结构标准](https://go.microsoft.com/fwlink/?LinkID=99212)和 Ecma International 网站上的[标准 ECMA-335 - 公共语言基础结构 (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataTables 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [IMetaDataTables2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
