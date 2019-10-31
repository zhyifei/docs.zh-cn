---
title: ETaskType 枚举
ms.date: 03/30/2017
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
ms.openlocfilehash: bc956827ad59fc655137e4147e6d98b6d097d470
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138193"
---
# <a name="etasktype-enumeration"></a>ETaskType 枚举
包含一些值，这些值指示由[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)或[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)接口表示的任务的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`TT_ADUNLOAD`|接口表示应用程序域卸载任务。|  
|`TT_DEBUGGERHELPER`|接口表示调试器帮助器任务。|  
|`TT_FINALIZER`|接口表示终结器任务。|  
|`TT_GC`|接口表示垃圾回收任务。|  
|`TT_THREADPOOL_GATE`|接口表示一个 "入口线程" 任务。|  
|`TT_THREADPOOL_IOCOMPLETION`|接口表示 i/o 线程任务或完成端口线程任务。|  
|`TT_THREADPOOL_TIMER`|接口表示计时器线程任务。|  
|`TT_THREADPOOL_WAIT`|接口表示等待线程任务。|  
|`TT_THREADPOOL_WORKER`|接口表示工作线程任务。|  
|`TT_UNKNOWN`|任务未知。|  
|`TT_USER`|接口表示用户任务。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
