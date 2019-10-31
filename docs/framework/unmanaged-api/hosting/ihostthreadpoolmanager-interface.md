---
title: IHostThreadPoolManager 接口
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: 8aef78c7cf70e6b2d97af9c47d57908b86729ff7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122074"
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager 接口
提供一些方法，使公共语言运行时（CLR）可以配置线程池并将工作项排队到线程池。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetAvailableThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|获取线程池中当前未处理工作项的线程的数目。|  
|[GetMaxThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|获取主机在线程池中并发维护的最大线程数。|  
|[GetMinThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|获取主机为获得请求而保留的空闲线程的最小数目。|  
|[QueueUserWorkItem 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|将函数排队以便执行，并提供包含函数要使用的数据的对象。|  
|[SetMaxThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|设置宿主可在线程池中维护的最大线程数。|  
|[SetMinThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|设置主机在预期请求中必须保持的空闲线程的最小数目。|  
  
## <a name="remarks"></a>备注  
 主机不需要使用对 `SetMaxThreads` 和 `SetMinThreads` 方法的调用中指定的值来配置线程池。 在这种情况下，宿主应从这些方法返回 E_NOTIMPL 的 HRESULT 值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
