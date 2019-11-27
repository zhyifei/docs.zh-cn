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
ms.openlocfilehash: 59512cc1c1b280d7fe6deb2f9d721ad53547e356
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437954"
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef 方法
获取一个指针，该指针指向成员引用的 MemberRef 标记，该成员引用由指定 <xref:System.Type> 包含并且具有指定的名称和元数据签名。  
  
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
  
## <a name="parameters"></a>参数  
 `td`  
 中类或接口的 TypeRef 标记，其中包含要搜索的成员引用。 如果 `mdTokenNil`此值，则将针对全局变量或全局函数引用来执行查找。  
  
 `szName`  
 中要搜索的成员引用的名称。  
  
 `pvSigBlob`  
 中指向成员引用的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 中`pvSigBlob`的大小（以字节为单位）。  
  
 `pmr`  
 弄指向匹配的 MemberRef 标记的指针。  
  
## <a name="remarks"></a>备注  
 使用成员的封闭类或接口（`td`）、其名称（`szName`）以及可选的签名（`pvSigBlob`）来指定成员。  
  
 传递给 `FindMemberRef` 的签名必须已在当前范围内生成，因为签名将绑定到特定范围。 签名可以嵌入标识封闭类或值类型的标记。 该令牌是本地 TypeDef 表中的索引。 不能在当前范围的上下文之外生成运行时签名，并使用该签名作为 `FindMemberRef`的输入。  
  
 `FindMemberRef` 仅查找直接在类或接口中定义的成员引用;它不会查找继承成员引用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
