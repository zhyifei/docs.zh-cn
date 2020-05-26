---
title: IHostControl::GetHostManager 方法
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
ms.openlocfilehash: 25e931ec17cad3508d548fb4ca7e53b0ade3f119
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804957"
---
# <a name="ihostcontrolgethostmanager-method"></a>IHostControl::GetHostManager 方法
获取一个接口指针，该指针指向具有指定的接口的主机实现 `IID` 。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a>参数  
 `riid`  
 中`IID`公共语言运行时（CLR）正在查询的接口的。  
  
 `ppObject`  
 弄指向宿主实现的接口的指针; 如果主机不支持此接口，则为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|`GetHostManager`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时，该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_INVALIDARG|请求的无效 `IID` 。|  
|E_NOINTERFACE|不支持请求的接口。|  
  
## <a name="remarks"></a>备注  
 CLR 将查询宿主，以确定它是否支持以下一个或多个接口：  
  
- [IHostMemoryManager](ihostmemorymanager-interface.md)  
  
- [IHostTaskManager](ihosttaskmanager-interface.md)  
  
- [IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)  
  
- [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)  
  
- [IHostSyncManager](ihostsyncmanager-interface.md)  
  
- [IHostAssemblyManager](ihostassemblymanager-interface.md)  
  
- [IHostGCManager](ihostgcmanager-interface.md)  
  
- [IHostPolicyManager](ihostpolicymanager-interface.md)  
  
- [IHostSecurityManager](ihostsecuritymanager-interface.md)  
  
 如果宿主支持指定的接口，它会将 `ppObject` 其设置为该接口的实现。 否则，它将设置 `ppObject` 为 null。  
  
 CLR 不会对 `Release` 主机管理器调用，即使您关闭它也是如此。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IHostControl 接口](ihostcontrol-interface.md)
