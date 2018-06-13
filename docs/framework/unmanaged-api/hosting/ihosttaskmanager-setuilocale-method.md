---
title: IHostTaskManager::SetUILocale 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f929dceafc72af89cfd85b1617de7bbd0bc0dfff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442737"
---
# <a name="ihosttaskmanagersetuilocale-method"></a>IHostTaskManager::SetUILocale 方法
通知主机公共语言运行时 (CLR) 已更改的用户界面 (UI) 区域设置或区域性，当前正在执行的任务。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a>参数  
 `lcid`  
 [in]映射到新分配的地理区域性和语言区域设置标识符值。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetUILocale` 已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_NOTIMPL|主机不允许托管的用户代码更改的 UI 区域性。|  
  
## <a name="remarks"></a>备注  
 在运行时调用`SetUILocale`时的值<xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>属性更改由托管代码。 此方法使宿主能够执行的区域设置的同步可能会显示任何机制有机会。 如果主机不允许使用要从托管代码中，更改的 UI 区域设置，或不实现一种机制来同步区域设置，则应从此方法返回 E_NOTIMPL。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [SetLocale 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
