---
title: IMetaDataFilter 接口
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440164"
---
# <a name="imetadatafilter-interface"></a>IMetaDataFilter 接口
提供用于标记和筛选元数据标记以避免重复已进行的操作的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[IsTokenMarked 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|Gets a value indicating whether the specified metadata token has been processed.|  
|[MarkToken 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|Sets a value indicating that the specified metadata token has been processed.|  
|[UnmarkAll 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|Removes the processing marks from all the tokens in the current metadata scope.|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
