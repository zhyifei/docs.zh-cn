---
title: "IHostSecurityManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44f2272c0f4e1423c222a004559d7bbd58237d82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager 接口
提供允许访问和控制当前正在执行的线程的安全上下文的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetSecurityContext 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|获取请求[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)从主机。|  
|[ImpersonateLoggedOnUser 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|请求的可执行代码，使用当前用户标识的凭据。|  
|[OpenThreadToken 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|将打开与当前线程关联的自定义访问令牌。|  
|[RevertToSelf 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|终止模拟当前用户标识，并返回原始线程令牌。|  
|[SetSecurityContext 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|设置当前执行线程的安全上下文。|  
|[SetThreadToken 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|设置当前执行线程的句柄。|  
  
## <a name="remarks"></a>备注  
 主机可以控制由公共语言运行时 (CLR) 和用户代码对线程标记的所有代码访问权限。 它还可确保完整的安全性在异步操作或具有受限制的代码访问权限的代码点间传递上下文信息。 `IHostSecurityContext`封装此安全上下文信息，这就是不透明的 CLR。  
  
 CLR 在内部处理托管的线程上下文。 它会查询特定于进程的`IHostSecurityManager`在以下情况：  
  
-   在终结器执行期间的终结器线程。  
  
-   在类和模块构造函数执行。  
  
-   在上工作线程，请调用异步点[ihostthreadpoolmanager:: Queueuserworkitem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)方法。  
  
-   处于维护的 I/O 完成端口。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IHostSecurityContext 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
