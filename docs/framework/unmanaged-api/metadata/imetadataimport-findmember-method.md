---
title: IMetaDataImport::FindMember 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177284"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember 方法
获取指向成员Def令牌的指针，用于指定<xref:System.Type>内容所包含且具有指定名称和元数据签名的字段或方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a>parameters  
 `td`  
 [在]包含要搜索的成员的类或接口的 TypeDef 令牌。 如果此值为`mdTokenNil`，则查找将执行全局变量或全局函数。  
  
 `szName`  
 [在]要搜索的成员的名称。  
  
 `pvSigBlob`  
 [在]指向成员的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 [在]的大小（以字节为单位）。 `pvSigBlob`  
  
 `pmb`  
 [出]指向匹配的会员Def令牌的指针。  
  
## <a name="remarks"></a>备注  
 您可以使用其封闭类或接口 （））`td``szName`指定成员，并选择其签名 （）。`pvSigBlob` 类或接口中可能有多个具有相同名称的成员。 在这种情况下，传递成员的签名以查找唯一匹配项。  
  
 传递给的签名`FindMember`必须在当前作用域中生成，因为签名绑定到特定作用域。 签名可以嵌入标识封闭类或值类型的令牌。 令牌是本地 TypeDef 表中的索引。 不能在当前作用域的上下文之外生成运行时签名，并且使用该签名作为输入 到`FindMember`的输入。  
  
 `FindMember`仅查找直接在类或接口中定义的成员;它找不到继承的成员。  
  
> [!NOTE]
> `FindMember`是帮助方法。 它调用[IMetaData 导入：：查找方法](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md);如果该呼叫找不到匹配项，`FindMember`则调用[IMetaDataImport：：FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
