---
title: "IMetaDataImport::EnumTypeDefs 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aeb0e3c2eab4cde219b050bcf0e50202fe2be3f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtypedefs-method"></a>IMetaDataImport::EnumTypeDefs 方法
枚举表示当前范围内的所有类型的 TypeDef 标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a>参数  
 `phEnum`  
 [out]新的枚举数指向的指针。 这必须在首次调用此方法为 NULL。  
  
 `rTypeDefs`  
 [in]用于存储 TypeDef 标记数组。  
  
 `cMax`  
 [in] `rTypeDefs` 数组的最大大小。  
  
 `pcTypeDefs`  
 [out]在中返回的 TypeDef 标记数`rTypeDefs`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs`已成功返回。|  
|`S_FALSE`|没有要枚举的标记。 在这种情况下，`pcTypeDefs`为零。|  
  
## <a name="remarks"></a>备注  
 的 TypeDef 标记表示的类型，例如类或接口，以及通过一种扩展机制添加任何类型。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
