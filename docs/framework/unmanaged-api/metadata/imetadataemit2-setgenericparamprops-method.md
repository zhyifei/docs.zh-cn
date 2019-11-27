---
title: IMetaDataEmit2::SetGenericParamProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: 7a93bbe0d7a9d9e6ff7505bbc215efa79176ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440446"
---
# <a name="imetadataemit2setgenericparamprops-method"></a>IMetaDataEmit2::SetGenericParamProps 方法
设置指定的标记所引用的泛型参数定义的属性值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `gp`  
 中要为其设置值的泛型参数定义的标记。  
  
 `dwParamFlags`  
 中描述泛型参数类型的[CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)枚举的值。  
  
 `szName`  
 [in] 可选。 要为其设置值的参数的名称。  
  
 `reserved`  
 中保留以供将来进行扩展。  
  
 `rtkConstraints`  
 [in] 可选。 类型约束的零终止数组。 数组成员必须是 `mdTypeDef`、`mdTypeRef`或 `mdTypeSpec` 元数据标记。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
