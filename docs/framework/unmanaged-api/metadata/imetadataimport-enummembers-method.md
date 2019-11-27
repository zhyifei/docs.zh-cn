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
ms.openlocfilehash: acb772a64c8f13405f2836bb5f4f308986dce414
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447652"
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
  
## <a name="parameters"></a>参数  
 `phEnum`  
 [in，out]指向枚举器的指针。  
  
 `cl`  
 中一个 TypeDef 标记，表示要枚举其成员的类型。  
  
 `rMembers`  
 弄用于保存 MemberDef 标记的数组。  
  
 `cMax`  
 [in] `rMembers` 数组的最大大小。  
  
 `pcTokens`  
 弄`rMembers`中返回的 MemberDef 令牌的实际数量。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` 成功返回。|  
|`S_FALSE`|没有要枚举的 MemberDef 令牌。 在这种情况下，`pcTokens` 为零。|  
  
## <a name="remarks"></a>备注  
 枚举类的成员集合时，`EnumMembers` 仅返回直接在类上定义的成员（字段和方法，但**不**是属性或事件）。 即使该类为这些继承成员提供了实现，它也不会返回类继承的任何成员。 若要枚举继承成员，调用方必须显式遍历继承链。 请注意，根据发出原始元数据的语言或编译器，继承链的规则可能会有所不同。
 
 `EnumMembers`不会枚举属性和事件。 若要枚举这些枚举，请使用[EnumProperties](imetadataimport-enumproperties-method.md)或[EnumEvents](imetadataimport-enumevents-method.md)。
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
