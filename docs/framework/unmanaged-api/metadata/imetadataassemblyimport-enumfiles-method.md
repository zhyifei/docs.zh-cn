---
title: IMetaDataAssemblyImport::EnumFiles 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43a895446e0070476bde3d15d332f010265176e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515032"
---
# <a name="imetadataassemblyimportenumfiles-method"></a>IMetaDataAssemblyImport::EnumFiles 方法
枚举当前程序集清单中引用的文件。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a>参数  
 `phEnum`  
 [in、 out]一个指向枚举器。 这必须是首次调用此方法的 null 值。  
  
 `rFiles`  
 [out]用于存储数组`mdFile`元数据标记。  
  
 `cMax`  
 [in]最大数目`mdFile`令牌可以置于`rFiles`。  
  
 `pcTokens`  
 [out]数`mdFile`令牌实际置于`rFiles`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|`EnumFiles` 已成功返回。|  
|`S_FALSE`|没有要枚举的标记。 在这种情况下，`pcTokens`设置为零。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
