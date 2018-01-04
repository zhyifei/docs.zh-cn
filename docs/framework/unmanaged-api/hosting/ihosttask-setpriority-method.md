---
title: "IHostTask::SetPriority 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.SetPriority
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2f9a57442b1671ef0286536215d10768636e3aa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttasksetpriority-method"></a>IHostTask::SetPriority 方法
表示由当前的任务的请求主机调整的线程优先级级别[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
#### <a name="parameters"></a>参数  
 `newPriority`  
 [in]一个整数，表示由当前的任务的请求的线程优先级值`IHostTask`实例。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetPriority`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 线程授予处理使用部分基于线程的优先级级别的轮循机制系统的时间。 `SetPriority`允许设置为当前的任务的线程优先级级别的 CLR。 以下`newPriority`支持值。  
  
-   THREAD_PRIORITY_ABOVE_NORMAL  
  
-   THREAD_PRIORITY_BELOW_NORMAL  
  
-   THREAD_PRIORITY_HIGHEST  
  
-   THREAD_PRIORITY_IDLE  
  
-   THREAD_PRIORITY_LOWEST  
  
-   THREAD_PRIORITY_NORMAL  
  
-   THREAD_PRIORITY_TIME_CRITICAL  
  
 CLR 调用`SetPriority`时的值<xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType>已由用户代码修改。 主机可以定义自己的线程优先级分配算法，并且可以自由地忽略此请求。  
  
> [!NOTE]
>  `SetPriority`不会报告是否进行了更改的线程优先级别。 调用[ihosttask:: Getpriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)以确定该任务的线程优先级级别的值。  
  
 定义由 Win32 线程优先级级别值`SetThreadPriority`函数。 有关线程优先级的详细信息，请参阅 Windows 平台文档。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading.Thread>  
 [ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [GetPriority 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)  
 [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
