---
title: "IMetaDataImport::EnumMembers 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMembers
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cc17437c18dd7a2cdc2fdabdc714b12f8d91cc7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummembers-method"></a>IMetaDataImport::EnumMembers 方法
枚举表示指定类型的成员的 MemberDef 标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a>参数  
 `phEnum`  
 [在中，out]枚举数指向的指针。  
  
 `cl`  
 [in]表示要枚举其成员的类型的 TypeDef 标记。  
  
 `rMembers`  
 [out]用来保存 MemberDef 标记数组。  
  
 `cMax`  
 [in] `rMembers` 数组的最大大小。  
  
 `pcTokens`  
 [out]在中返回的 MemberDef 标记的实际数`rMembers`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers`已成功返回。|  
|`S_FALSE`|没有要枚举的 MemberDef 标记。 在这种情况下，`pcTokens`为零。|  
  
## <a name="remarks"></a>备注  
 枚举的成员的类集合时`EnumMembers`返回仅直接在类上定义的成员。 即使此类提供这些继承成员的实现，它不返回此类继承，任何成员。 若要枚举继承的成员，调用方必须显式引导继承链。 请注意，继承链的规则可能会有所不同，具体取决于语言或发出的原始元数据的编译器。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
