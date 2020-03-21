---
title: IMetaDataTables::GetColumn 方法
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177143"
---
# <a name="imetadatatablesgetcolumn-method"></a>IMetaDataTables::GetColumn 方法
获取指向给定表中指定列和行单元格中包含的值的指针。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a>parameters

 `ixTbl`  
 [在]表的索引。  
  
 `ixCol`  
 [在]表中列的索引。  
  
 `rid`  
 [在]表中行的索引。  
  
 `pVal`  
 [出]指向单元格中值的指针。  

## <a name="remarks"></a>备注

返回的值的解释`pVal`取决于列的类型。 可以通过调用[IMetaDataTables](imetadatatables-getcolumninfo-method.md)来确定列类型。

- **GetColumn**方法会自动将 **"Rid"** 或"**编码令牌"** 类型的列转换为完整的 32 位`mdToken`值。
- 它还会自动将 8 位或 16 位值转换为完整的 32 位值。
- 对于*堆*类型列，返回的*pVal*将是相应堆中的索引。

| 列类型              | pVal 包含 | 注释                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)  | mdToken     | *pVal*将包含一个完整的令牌。 该函数会自动将 Rid 转换为完整令牌。 |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | mdToken | 返回后 *，pVal*将包含一个完整的令牌。 该函数会自动将编码令牌解压缩为完整令牌。 |
| `iSHORT`(96)            | Int16         | 自动签名扩展到 32 位。  |
| `iUSHORT`(97)           | UInt16        | 自动签名扩展到 32 位。  |
| `iLONG`(98)             | Int32         |                                        |
| `iULONG`(99)            | UInt32        |                                        |
| `iBYTE`(100)            | Byte          | 自动签名扩展到 32 位。  |
| `iSTRING`(101)          | 字符串堆索引 | *pVal*是字符串堆中的索引。 使用[IMetadataTables：：获取String](imetadatatables-getstring-method.md)获取实际列字符串值。 |
| `iGUID`(102)            | 吉德堆索引 | *pVal*是 Guid 堆中的索引。 使用[IMetadataTables：：getGuid](imetadatatables-getguid-method.md)获取实际列 Guid 值。 |
| `iBLOB`(103)            | Blob 堆索引 | *pVal*是 Blob 堆中的索引。 使用[IMetadataTables：：获取 Blob](imetadatatables-getblob-method.md)获取实际列 Blob 值。 |
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataTables 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
