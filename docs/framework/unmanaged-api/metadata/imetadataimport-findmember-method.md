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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4eefb7ec1e7d0d130ec64531a59d1d5bbce04963
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968920"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember 方法
获取一个指针, 该指针指向由指定的和具有指定名称和元数据<xref:System.Type>签名的指定的 MemberDef 标记。  
  
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
  
## <a name="parameters"></a>参数  
 `td`  
 中包含要搜索的成员的类或接口的 TypeDef 标记。 如果此值为`mdTokenNil`, 则对全局变量或全局函数执行查找。  
  
 `szName`  
 中要搜索的成员的名称。  
  
 `pvSigBlob`  
 中指向成员的二进制元数据签名的指针。  
  
 `cbSigBlob`  
 中的大小 (以字节`pvSigBlob`为单位)。  
  
 `pmb`  
 弄指向匹配的 MemberDef 标记的指针。  
  
## <a name="remarks"></a>备注  
 使用成员的封闭类或接口 (`td`)、其名称 (`szName`) 和 (可选) 的签名 (`pvSigBlob`) 来指定成员。 类或接口中可能存在多个具有相同名称的成员。 在这种情况下, 传递成员的签名以查找唯一匹配项。  
  
 传递给`FindMember`的签名必须已在当前范围内生成, 因为签名将绑定到特定范围。 签名可以嵌入标识封闭类或值类型的标记。 该令牌是本地 TypeDef 表中的索引。 不能在当前范围的上下文之外生成运行时签名, 并将该签名用作输入以输入到`FindMember`。  
  
 `FindMember`仅查找直接在类或接口中定义的成员;它不会查找继承成员。  
  
> [!NOTE]
> `FindMember`是一个帮助器方法。 它调用[IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md);如果该调用找不到匹配项, `FindMember`则调用[IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
