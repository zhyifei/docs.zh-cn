---
title: WAIT_OPTION 枚举
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141513"
---
# <a name="wait_option-enumeration"></a>WAIT_OPTION 枚举
包含一些值，这些值指示当公共语言运行时（CLR）块请求的操作时宿主应执行的操作。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|如果 CLR 调用[IHostTask：： Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)方法，则通知宿主应唤醒任务。|  
|`WAIT_MSGPUMP`|当线程被阻止时，通知宿主必须在当前 OS 线程上抽取消息。 运行时仅在 <xref:System.Threading.ApartmentState.STA> 线程上指定此值。|  
|`WAIT_NOTINDEADLOCK`|向宿主通知指定的同步请求无法被宿主中断。 也就是说，主机不能返回 `HOST_E_DEADLOCK`。|  
  
## <a name="remarks"></a>备注  
 [IHostTaskManager：： Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)和[IHostTaskManager：： SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)方法都采用此类型的参数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
