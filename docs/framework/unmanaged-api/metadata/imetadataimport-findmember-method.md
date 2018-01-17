---
title: "IMetaDataImport::FindMember 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMember
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a20930688aed210309a719de2c7187f1f5fd1f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember 方法
获取一个指针 MemberDef 标记的字段或方法包含指定<xref:System.Type>并具有指定的名称和元数据签名。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a>参数  
 `td`  
 [in]对类或接口包含要搜索的成员的 TypeDef 标记。 如果此值为`mdTokenNil`，对全局变量或全局函数执行查找。  
  
 `szName`  
 [in]要搜索的成员名称。  
  
 `pvSigBlob`  
 [in]指向成员的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 [in]以字节为单位的大小`pvSigBlob`。  
  
 `pmb`  
 [out]指向匹配的 MemberDef 标记的指针。  
  
## <a name="remarks"></a>备注  
 指定使用其封闭类或接口的成员 (`td`)，其名称 (`szName`)，（可选） 及其签名 (`pvSigBlob`)。 可能有多个具有相同名称的类或接口中的成员。 在这种情况下，传递的成员的签名，以查找唯一匹配项。  
  
 签名传递给`FindMember`必须已生成在当前范围内，因为签名绑定到特定的作用域。 签名中可以嵌入标识封闭类或值类型的令牌。 该标记是本地的 TypeDef 表中的索引。 不能生成上下文之外的当前作用域的运行时签名并使用该签名为的输入`FindMember`。  
  
 `FindMember`查找直接在类或接口; 中定义的成员找不到继承的成员。  
  
> [!NOTE]
>  `FindMember`是一个帮助器方法。 它调用[imetadataimport:: Findmethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); 如果该调用未找到匹配项，`FindMember`然后调用[imetadataimport:: Findfield](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
