---
title: IMetaDataImport::FindMemberRef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175416"
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef 方法
获取指向成员参考的指向成员Ref 令牌的指针，该引用由指定内容<xref:System.Type>所封闭，并且具有指定的名称和元数据签名。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a>parameters  
 `td`  
 [在]包含要搜索的成员引用的类或接口的 TypeRef 令牌。 如果此值为`mdTokenNil`，则查找将执行全局变量或全局函数引用。  
  
 `szName`  
 [在]要搜索的成员引用的名称。  
  
 `pvSigBlob`  
 [在]指向成员引用的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 [在]的大小（以字节为单位）。 `pvSigBlob`  
  
 `pmr`  
 [出]指向匹配的会员Ref令牌的指针。  
  
## <a name="remarks"></a>备注  
 您可以使用其封闭类或接口 （））`td``szName`指定成员，并选择其签名 （）。`pvSigBlob`  
  
 传递给的签名`FindMemberRef`必须在当前作用域中生成，因为签名绑定到特定作用域。 签名可以嵌入标识封闭类或值类型的令牌。 令牌是本地 TypeDef 表中的索引。 不能在当前作用域的上下文之外生成运行时签名，并且使用该签名作为 输入`FindMemberRef`。  
  
 `FindMemberRef`仅查找直接在类或接口中定义的成员引用;它找不到继承的成员引用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
