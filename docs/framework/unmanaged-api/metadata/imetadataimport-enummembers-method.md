---
title: IMetaDataImport::EnumMembers 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175481"
---
# <a name="imetadataimportenummembers-method"></a>IMetaDataImport::EnumMembers 方法
枚举表示指定类型的成员的 MemberDef 标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>parameters  
 `phEnum`  
 [进出]指向枚举器的指针。  
  
 `cl`  
 [在]表示要枚举其成员的类型的类型的类型的类型。  
  
 `rMembers`  
 [出]用于保存成员Def令牌的数组。  
  
 `cMax`  
 [in] `rMembers` 数组的最大大小。  
  
 `pcTokens`  
 [出]在 中`rMembers`返回的会员Def令牌的实际数量。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers`已成功返回。|  
|`S_FALSE`|没有要枚举的会员Def令牌。 在这种情况下，`pcTokens`为零。|  
  
## <a name="remarks"></a>备注  
 枚举类成员的集合时，`EnumMembers`仅返回直接在类上定义的成员（字段和方法，**但不包括**属性或事件）。 它不返回类继承的任何成员，即使类为这些继承成员提供了实现也是如此。 要枚举继承的成员，调用方必须显式遍历继承链。 请注意，继承链的规则可能因发出原始元数据的语言或编译器而异。

 属性和事件不由 枚举`EnumMembers`枚举。 要枚举这些，请使用[枚举属性](imetadataimport-enumproperties-method.md)或[枚举事件](imetadataimport-enumevents-method.md)。
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
