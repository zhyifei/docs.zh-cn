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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f256195a4cd5b18f568e05156db867aa5dba9161
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229818"
---
# <a name="etasktype-enumeration"></a>ETaskType 枚举
包含指示表示通过以下任一方法的任务的类型值[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)或[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)接口。  
  
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
|`TT_ADUNLOAD`|该接口表示应用程序域正在卸载任务。|  
|`TT_DEBUGGERHELPER`|该接口表示调试器帮助程序任务。|  
|`TT_FINALIZER`|该接口表示终结器任务。|  
|`TT_GC`|该接口表示垃圾回收任务。|  
|`TT_THREADPOOL_GATE`|该接口表示入口线程任务。|  
|`TT_THREADPOOL_IOCOMPLETION`|该接口表示一个 I/O 线程任务或完成端口线程任务。|  
|`TT_THREADPOOL_TIMER`|该接口表示计时器线程任务。|  
|`TT_THREADPOOL_WAIT`|该接口表示等待线程任务。|  
|`TT_THREADPOOL_WORKER`|该接口表示工作线程任务。|  
|`TT_UNKNOWN`|该任务是未知的。|  
|`TT_USER`|该接口表示一个用户任务。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
