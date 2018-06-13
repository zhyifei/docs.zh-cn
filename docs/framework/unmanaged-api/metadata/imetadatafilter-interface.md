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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad77aba02c819749794534ca2ecd478661bc363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444976"
---
# <a name="imetadatafilter-interface"></a>IMetaDataFilter 接口
提供用于标记和筛选元数据标记以避免重复已进行的操作的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[IsTokenMarked 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|获取一个值，该值指示是否已处理的指定元数据标记。|  
|[MarkToken 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|设置一个值，该值指定元数据标记已被处理。|  
|[UnmarkAll 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|从当前的元数据范围内的所有令牌中移除处理标记。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
