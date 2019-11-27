---
title: IMetaDataAssemblyImport::EnumAssemblyRefs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 06b81615565a04db7d6cfef4da9b5372a85afd68
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450343"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a>IMetaDataAssemblyImport::EnumAssemblyRefs 方法
枚举程序集清单中定义的 `mdAssemblyRef` 实例。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>参数  
 `phEnum`  
 [in，out]指向枚举器的指针。 当首次调用 `EnumAssemblyRefs` 方法时，此值必须为 null 值。  
  
 `rAssemblyRefs`  
 弄`mdAssemblyRef` 元数据标记的枚举。  
  
 `cMax`  
 中可放置在 `rAssemblyRefs` 数组中的标记的最大数目。  
  
 `pcTokens`  
 弄实际置于 `rAssemblyRefs`中的标记数。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` 成功返回。|  
|`S_FALSE`|没有要枚举的令牌。 在这种情况下，`pcTokens` 设置为零。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
