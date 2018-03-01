---
title: "IMetaDataValidate::ValidatorInit 方法"
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
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26f5f6626766d7341ef5c8b2ecbe5e56a17eafdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatavalidatevalidatorinit-method"></a>IMetaDataValidate::ValidatorInit 方法
设置一个标志，该标志指定当前元数据范围内的模块类型，并注册验证错误的指定回调方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwModule`  
 [in]值为[CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md)枚举当前元数据范围内指定的模块类型。  
  
 `pUnk`  
 [in]一个指向 <<!--zzxref:IUnknown --> `IUnknown`> 用作验证错误回调函数的实例。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataValidate 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
