---
title: "ICLROnEventManager::RegisterActionOnEvent 方法"
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
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 008bdc856c9fbede7398f467674ac191c1860128
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a>ICLROnEventManager::RegisterActionOnEvent 方法
注册指定的事件的回调指针。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a>参数  
 `event`  
 [in]之一[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)值，指示要为其注册回调指针所描述事件`pAction`。  
  
 `pAction`  
 [in]指向的指针[IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)时，已注册的事件将激发调用的对象。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`RegisterActionOnEvent`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 主机可以注册一个或两个所描述的两个事件类型的回调`EClrEvent`。 主机获取`ICLROnEventManager`接口通过调用[iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法。  
  
> [!NOTE]
>  事件的`RegisterActionOnEvent`不止一次和从不同的线程，以卸载或禁用 CLR 发出信号，则可以激发寄存器。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [EClrEvent 枚举](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [IActionOnCLREvent 接口](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLROnEventManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
