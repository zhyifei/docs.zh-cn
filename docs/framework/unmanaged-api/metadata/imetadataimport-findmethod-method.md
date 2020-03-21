---
title: IMetaDataImport::FindMethod 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177255"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod 方法
获取指向方法的指针，该方法由指定内容<xref:System.Type>封闭，并且具有指定的名称和元数据签名。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>parameters  
 `td`  
 [在]包含`mdTypeDef`要搜索的成员的类型（类或接口）的令牌。 如果此值为`mdTokenNil`，则对全局函数执行查找。  
  
 `szName`  
 [在]要搜索的方法的名称。  
  
 `pvSigBlob`  
 [在]指向方法的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 [在]的大小（以字节为单位）。 `pvSigBlob`  
  
 `pmb`  
 [出]指向匹配的 MethodDef 令牌的指针。  
  
## <a name="remarks"></a>备注  
 使用其封闭类或接口 （））`td``szName`和可选方式指定方法的签名 （）。`pvSigBlob` 类或接口中可能有多个同名方法。 在这种情况下，传递方法的签名以查找唯一匹配项。  
  
 传递给的签名`FindMethod`必须在当前作用域中生成，因为签名绑定到特定作用域。 签名可以嵌入标识封闭类或值类型的令牌。 令牌是本地 TypeDef 表中的索引。 不能在当前作用域的上下文之外生成运行时签名，并且使用该签名作为输入 到`FindMethod`的输入。  
  
 `FindMethod`仅查找直接在类或接口中定义的方法;它找不到继承的方法。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
