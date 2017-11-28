---
title: "IHostTaskManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager
helpviewer_keywords: IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a5086f3349b3756e507855a87bd724d2618212f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager 接口
提供允许公共语言运行时 (CLR) 用于通过主机而不是使用标准操作系统线程处理或纤程函数的任务的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[BeginDelayAbort 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|通知宿主托管代码正在进入不能在其中中止当前任务的周期。|  
|[BeginThreadAffinity 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|通知宿主托管代码正在进入在其中将当前的任务必须不移动到另一个操作系统线程的周期。|  
|[CallNeedsHostHook 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|使主机可以指定公共语言运行时是否可以内联到非托管函数的指定调用。|  
|[CreateTask 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|主机创建一个新的任务的请求。|  
|[EndDelayAbort 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|通知宿主托管代码正在退出在其中不必须中止当前的任务，周期以下以前调用`BeginDelayAbort`。|  
|[EndThreadAffinity 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|通知宿主托管代码正在退出不能在其中当前任务移动到另一个操作系统线程，周期以下以前调用`BeginThreadAffinity`。|  
|[EnterRuntime 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|通知主机的调用非托管方法，如平台调用方法，是执行将控制返回到 CLR。|  
|[GetCurrentTask 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|获取从中进行此调用的操作系统线程当前正在执行的任务的接口指针。|  
|[GetStackGuarantee 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|获取量的保证将之后堆栈操作完成，可用的堆栈空间但在进程结束之前。|  
|[LeaveRuntime 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|通知宿主托管代码将要对非托管函数进行调用。|  
|[ReverseEnterRuntime 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|通知主机正在到公共语言运行时 (CLR) 从非托管代码进行调用。|  
|[ReverseLeaveRuntime 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|通知主机控制正在离开 CLR 并输入从托管代码调用非托管的函数。|  
|[SetCLRTaskManager 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|为宿主提供的接口指针到[ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)由 CLR 实现的实例。|  
|[SetLocale 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|通知主机 CLR 已更改了当前任务中的区域设置。|  
|[SetStackGuarantee 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|保留以仅供内部使用。|  
|[SetUILocale 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|通知主机用户界面区域设置已在当前任务。|  
|[Sleep 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|通知宿主，当前的任务将进入睡眠状态。|  
|[SwitchToTask 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|通知主机应该换出当前任务。|  
  
## <a name="remarks"></a>备注  
 `IHostTaskManager`允许 CLR 创建和管理任务，若要提供的主机时要执行操作控制从托管代码转换到非托管代码，反之亦然，并指定特定操作的挂钩主机可以才能在代码执行过程。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
