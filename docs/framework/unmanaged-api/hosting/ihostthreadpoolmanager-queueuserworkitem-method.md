---
title: IHostThreadPoolManager::QueueUserWorkItem 方法
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b458739db024bdbe8cf0fb5a12a5d5f508d332da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441716"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a>IHostThreadPoolManager::QueueUserWorkItem 方法
排队的执行，函数，并指定包含数据以供该函数的对象。 在有线程变得可用时，将执行该函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `Function`  
 [in]表示要执行的函数的函数指针。  
  
 `Context`  
 [in]包含使用的数据的对象`Function`。  
  
 `Flags`  
 [in]其中一个标志的值，如定义为 Win32`QueueUserWorkItem`方法，以控制执行。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`QueueUserWorkItem` 已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `QueueUserWorkItem` 排队到线程池的工作线程的工作项。 其签名和参数类型是相应的 Win32 函数具有相同的名称相同。 有关详细信息，请参阅 Windows 平台文档。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ThreadPool>  
 [IHostThreadPoolManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
