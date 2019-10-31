---
title: IHostSecurityContext 接口
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: 993d16818b25dfefe1f53c7afd06bc9857d9eb24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121525"
---
# <a name="ihostsecuritycontext-interface"></a>IHostSecurityContext 接口
允许公共语言运行时（CLR）维护宿主实现的安全上下文信息。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Capture 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|获取从对[IHostSecurityManager：： GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)的调用返回的 `IHostSecurityContext` 实例的克隆。|  
  
## <a name="remarks"></a>备注  
 宿主可以通过 CLR 和用户代码控制对线程标记的所有代码访问。 它还可以确保在异步操作或代码点之间跨受限制的代码访问传递完整的安全上下文信息。 `IHostSecurityContext` 封装此安全上下文信息，这对于运行时是不透明的。 运行时使用 `Capture`捕获此信息，并将其移动到线程池辅助角色项调度、终结器执行和模块和类构造函数中。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRHostProtectionManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [IHostSecurityManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
