---
title: IMetaDataImport::EnumMemberRefs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 444c892026f9b6de12255ebdcda829db82c9bfdb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780442"
---
# <a name="imetadataimportenummemberrefs-method"></a>IMetaDataImport::EnumMemberRefs 方法
枚举表示指定类型成员的 MemberRef 标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a>参数  
 `phEnum`  
 [in、 out]一个指向枚举器。  
  
 `tkParent`  
 [in]要枚举其成员的类型的 TypeDef、 TypeRef、 MethodDef 或 ModuleRef 标记。  
  
 `rMemberRefs`  
 [out]用于存储 MemberRef 令牌的数组。  
  
 `cMax`  
 [in] `rMemberRefs` 数组的最大大小。  
  
 `pcTokens`  
 [out]MemberRef 令牌中返回的实际数目`rMemberRefs`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|`EnumMemberRefs` 已成功返回。|  
|`S_FALSE`|没有要枚举的 MemberRef 标记。 在这种情况下，`pcTokens`是为零。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 包含为 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
