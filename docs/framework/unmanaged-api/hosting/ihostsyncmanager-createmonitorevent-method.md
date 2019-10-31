---
title: IHostSyncManager::CreateMonitorEvent 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
ms.openlocfilehash: f7426585045c7ae81377ec9bfca9d397d6f734cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192022"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a>IHostSyncManager::CreateMonitorEvent 方法
创建监视的自动重置事件对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>参数  
 `cookie`  
 中要与事件对象关联的 cookie。  
  
 `ppEvent`  
 弄指向[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实例的地址的指针; 如果无法创建事件对象，则为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`CreateMonitorEvent` 成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时，该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_OUTOFMEMORY|没有足够的内存可用于创建请求的事件对象。|  
  
## <a name="remarks"></a>备注  
 `CreateMonitorEvent` 返回 CLR 在其托管 <xref:System.Threading.Monitor?displayProperty=nameWithType> 类型实现中使用的 `IHostAutoEvent`。 此方法会镜像 Win32 `CreateEvent` 函数，并为 `bManualReset` 参数指定 `false` 值。  
  
 主机可以通过调用[ICLRSyncManager：： GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)方法来使用 cookie 来确定在监视器上正在等待的任务。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostAutoEvent 接口](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [IHostSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
