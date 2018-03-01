---
title: "CoInitializeEE 函数"
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
- CoInitializeEE
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ca564830411a9df0d47cc9765958286bbd40f96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="coinitializeee-function"></a>CoInitializeEE 函数
确保公共语言运行时执行引擎已加载到进程。 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。 使用[iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fFlags`  
 [in]之一[COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md)枚举常量。  
  
## <a name="return-value"></a>返回值  
 Winerror.h 和下表中的值中定义，此方法将返回标准的 COM 错误代码。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|执行引擎已成功加载。|  
|S_FALSE|执行引擎已加载。|  
|E_FAIL|无法加载执行引擎。|  
  
## <a name="remarks"></a>备注  
 如果它尚未以前加载，则此方法将加载的执行引擎。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
