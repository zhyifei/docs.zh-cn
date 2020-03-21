---
title: IMetaDataImport::GetInterfaceImplProps 方法
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175377"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>IMetaDataImport::GetInterfaceImplProps 方法
获取实现指定方法的 的 元数据<xref:System.Type>令牌以及声明该方法的接口的指针。
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a>parameters  
 `iiImpl`  
 [在]表示要返回类和接口令牌的方法的元数据令牌。  
  
 `pClass`  
 [出]表示实现方法的类的元数据令牌。  
  
 `ptkIface`  
 [出]表示定义已实现方法的接口的元数据令牌。  

## <a name="remarks"></a>备注

 通过调用`iImpl`[EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md)方法，可以获取 的值。

 例如，假设一个类的`mdTypeDef`令牌值为 0x02000007，并且它实现了三个接口，其类型具有令牌：

- 0x0200003 （类型定义）
- 0x0100000A （类型参考）
- 0x0200001C （类型定义）

从概念上讲，此信息存储在接口实现表中，如：

| 行号 | 类令牌 | 接口令牌 |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

回想，令牌是 4 字节的值：

- 较低的 3 个字节保留行号或 RID。
- 上字节保存的令牌类型 = 0x09。 `mdtInterfaceImpl`

`GetInterfaceImplProps`返回您在`iImpl`参数中提供的令牌行中持有的信息。
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
