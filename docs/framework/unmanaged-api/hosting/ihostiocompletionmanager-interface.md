---
title: IHostIoCompletionManager 接口
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 51d79c398c94ec355528140325da2c25422cbad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133848"
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager 接口
提供允许公共语言运行时（CLR）与主机提供的 i/o 完成端口进行交互的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Bind 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|将句柄绑定到 i/o 完成端口。|  
|[CloseIoCompletionPort 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|关闭通过之前对 `CreateIoCompletionPort`的调用创建的端口。|  
|[CreateIoCompletionPort 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|请求宿主创建新的 i/o 完成端口。|  
|[GetAvailableThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|获取当前未处理请求的 i/o 完成线程数。|  
|[GetHostOverlappedSize 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|获取宿主打算追加到 i/o 请求的任何自定义数据的大小。|  
|[GetMaxThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|获取主机可为服务 i/o 请求分配的最大线程数。|  
|[GetMinThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|获取主机提供的用于处理 i/o 请求的最小线程数。|  
|[InitializeHostOverlapped 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|向宿主提供初始化有关 i/o 请求的任何自定义数据的机会。|  
|[SetCLRIoCompletionManager 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|向宿主提供一个接口指针，该指针指向 CLR 实现的[ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)实例。|  
|[SetMaxThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|设置主机 allots i/o 请求的最大线程数。|  
|[SetMinThreads 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|设置主机应为 i/o 完成分配的最小线程数。|  
  
## <a name="remarks"></a>备注  
 `IHostIoCompletionManager` 对应于 CLR 实现的 `ICLRIoCompletionManager` 接口。 CLR 调用 `IHostIoCompletionManager` 的方法将句柄绑定到主机提供的端口，主机调用 `ICLRIoCompletionManager` 的方法来报告 i/o 请求的完成。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
