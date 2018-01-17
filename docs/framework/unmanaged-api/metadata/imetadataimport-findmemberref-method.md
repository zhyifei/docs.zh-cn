---
title: "IMetaDataImport::FindMemberRef 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMemberRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a94fb09e1ff62abac9dd716257ba75542453707e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef 方法
获取指向成员的 MemberRef 标记的引用，它是括在指定<xref:System.Type>并具有指定的名称和元数据签名。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a>参数  
 `td`  
 [in]对类或接口包含要搜索的成员引用的 TypeRef 标记。 如果此值为`mdTokenNil`，全局变量或全局函数引用执行查找。  
  
 `szName`  
 [in]要搜索的成员引用的名称。  
  
 `pvSigBlob`  
 [in]指向成员引用的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 [in]以字节为单位的大小`pvSigBlob`。  
  
 `pmr`  
 [out]指向匹配的 MemberRef 标记的指针。  
  
## <a name="remarks"></a>备注  
 指定使用其封闭类或接口的成员 (`td`)，其名称 (`szName`)，（可选） 及其签名 (`pvSigBlob`)。  
  
 签名传递给`FindMemberRef`必须已生成在当前范围内，因为签名绑定到特定的作用域。 签名中可以嵌入标识封闭类或值类型的令牌。 该标记是本地的 TypeDef 表中的索引。 无法生成上下文之外的当前作用域的运行时签名并使用该签名作为输入`FindMemberRef`。  
  
 `FindMemberRef`查找仅成员直接在类或接口; 中定义的引用找不到继承的成员的引用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
