---
title: "IMetaDataImport::FindMethod 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e59cc440ba004545c31d6b25d36cca4fdfb58899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod 方法
获取一个指向 methoddef 标记包含的方法由指定<xref:System.Type>并具有指定的名称和元数据签名。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
#### <a name="parameters"></a>参数  
 `td`  
 [in]`mdTypeDef`标记，表示包含要搜索的成员的类型 （类或接口）。 如果此值为`mdTokenNil`，然后对全局函数执行查找。  
  
 `szName`  
 [in]要搜索的方法名称。  
  
 `pvSigBlob`  
 [in]指向方法的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 [in]以字节为单位的大小`pvSigBlob`。  
  
 `pmb`  
 [out]指向匹配的 MethodDef 标记的指针。  
  
## <a name="remarks"></a>备注  
 指定使用其封闭类或接口的方法 (`td`)，其名称 (`szName`)，（可选） 及其签名 (`pvSigBlob`)。 可能有多个具有相同名称的类或接口中的方法。 在这种情况下，将传递方法的签名，以查找唯一匹配项。  
  
 签名传递给`FindMethod`必须已生成在当前范围内，因为签名绑定到特定的作用域。 签名中可以嵌入标识封闭类或值类型的令牌。 该标记是本地的 TypeDef 表中的索引。 不能生成上下文之外的当前作用域的运行时签名并使用该签名为的输入`FindMethod`。  
  
 `FindMethod`查找直接在类或接口; 中定义的方法未找到继承的方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Reflection.MethodInfo>  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
