---
title: "IHostFilter::MarkToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostFilter.MarkToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca342e04f554d070546c6c6d82d5ad56a4dad8cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostfiltermarktoken-method"></a>IHostFilter::MarkToken 方法
指示将处理指定元数据标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
#### <a name="parameters"></a>参数  
 `tk`  
 [in]要处理的元数据标记。  
  
## <a name="remarks"></a>备注  
 通常情况下，你想要处理如果在元数据范围内的令牌。 `MarkToken`方法传递给元数据引擎通过[imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IHostFilter 方法](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
