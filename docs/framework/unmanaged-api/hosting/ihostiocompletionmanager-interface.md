---
title: "IHostIoCompletionManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager
helpviewer_keywords: IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 847d4c3aa3e3da94b4aac4679ada047577379f82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager 接口
提供允许公共语言运行时 (CLR) 与主机提供的 I/O 完成端口进行交互的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Bind 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|将句柄绑定到 I/O 完成端口。|  
|[CloseIoCompletionPort 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|关闭通过以前调用创建的端口`CreateIoCompletionPort`。|  
|[CreateIoCompletionPort 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|主机创建新的 I/O 完成端口的请求。|  
|[GetAvailableThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|获取当前不在处理请求的 I/O 完成线程数。|  
|[GetHostOverlappedSize 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|获取宿主要追加到输入/输出请求的任何自定义数据的大小。|  
|[GetMaxThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|获取服务输入/输出请求的最大主机可以分配的线程数。|  
|[GetMinThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|获取服务输入/输出请求的最小主机提供的线程数。|  
|[InitializeHostOverlapped 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|若要初始化的 I/O 请求有关的任何自定义数据的机会提供主机。|  
|[SetCLRIoCompletionManager 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|为宿主提供的接口指针到[ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)由 CLR 实现的实例。|  
|[SetMaxThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|将最大主机分配的线程数设置为服务输入/输出请求。|  
|[SetMinThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|将最小应分配主机的线程数设置为 I/O 完成。|  
  
## <a name="remarks"></a>备注  
 `IHostIoCompletionManager`对应于`ICLRIoCompletionManager`由 CLR 实现接口。 CLR 调用的方法`IHostIoCompletionManager`将句柄绑定到主机提供，并且宿主调用的方法的端口`ICLRIoCompletionManager`报告 I/O 请求的完成。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
