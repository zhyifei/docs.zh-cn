---
title: "IHostThreadPoolManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager
helpviewer_keywords: IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2773042c695320ab1e90d4c5d341e2df5f0f778f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager 接口
提供启用公共语言运行时 (CLR) 若要配置线程池以及排队到线程池工作项的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetAvailableThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|获取在当前不在处理工作项的线程池中的线程数。|  
|[GetMaxThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|在线程池中同时获取最大主机维护的线程数。|  
|[GetMinThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|预期的请求中获取的最小主机维护的空闲线程数。|  
|[QueueUserWorkItem 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|排队的执行，函数，并提供一个包含由该函数使用的数据的对象。|  
|[SetMaxThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|设置最大主机可以维护在线程池中的线程数。|  
|[SetMinThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|预期的请求中设置的最小主机必须维护的空闲线程数。|  
  
## <a name="remarks"></a>备注  
 主机不需要使用对的调用中指定的值配置线程池`SetMaxThreads`和`SetMinThreads`方法。 在这种情况下，主机应从这些方法返回 E_NOTIMPL 的 HRESULT 值。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
