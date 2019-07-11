---
title: ICorThreadpool::CorQueueUserWorkItem 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b421825c7a1f0a42d9b54e36a8e8c1dce2c1fd76
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751178"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a>ICorThreadpool::CorQueueUserWorkItem 方法
此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 包含为 MSCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorThreadpool 接口](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
