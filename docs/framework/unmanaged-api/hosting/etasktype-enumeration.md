---
title: "ETaskType 枚举"
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
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7973b8cbd49858daaf6f08d55c7d9f60f687a72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="etasktype-enumeration"></a>ETaskType 枚举
包含值，用于指示表示通过以下任一方法的任务的类型[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)或[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)接口。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`TT_ADUNLOAD`|接口表示一个应用程序域卸载任务。|  
|`TT_DEBUGGERHELPER`|接口表示调试器帮助程序任务。|  
|`TT_FINALIZER`|接口表示终结器任务。|  
|`TT_GC`|接口表示垃圾回收作业。|  
|`TT_THREADPOOL_GATE`|接口表示入口线程任务。|  
|`TT_THREADPOOL_IOCOMPLETION`|接口表示一个 I/O 线程任务或完成端口线程任务。|  
|`TT_THREADPOOL_TIMER`|接口表示计时器线程任务。|  
|`TT_THREADPOOL_WAIT`|接口表示等待线程任务。|  
|`TT_THREADPOOL_WORKER`|接口表示一个工作线程任务。|  
|`TT_UNKNOWN`|任务是未知的。|  
|`TT_USER`|接口表示一个用户任务。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
