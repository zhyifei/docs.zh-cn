---
title: "ICLRIoCompletionManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99dc183674abaff33047f070c14794150a8615f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanager-interface"></a>ICLRIoCompletionManager 接口
实现一个回调方法，指定的 I/O 的状态以便通知公共语言运行时 (CLR) 主机请求。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[OnComplete 方法](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|通知由调用的 I/O 请求的状态的 CLR [ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)方法。|  
  
## <a name="remarks"></a>备注  
 主机通过使用实现的 I/O 完成抽象[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)接口。 CLR 通过此接口，使输入/输出请求和主机通知此类请求的结果的运行时通过使用`ICLRIoCompletionManager`接口。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IHostIoCompletionManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [IHostThreadPoolManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
