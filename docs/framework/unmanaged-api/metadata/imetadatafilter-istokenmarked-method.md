---
title: IMetaDataFilter::IsTokenMarked 方法
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6969f2c1df9b5b04122ed6aef550697171123cf5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992493"
---
# <a name="imetadatafilteristokenmarked-method"></a>IMetaDataFilter::IsTokenMarked 方法
获取一个值，该值指示指定的元数据令牌是否已标记为已处理。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a>参数  
 `tk`  
 [in]要检查其处理标记的标记。  
  
 `pIsMarked`  
 [out]一个值，则该值`true`如果`tk`处理; 否则为`false`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IMetaDataFilter 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
