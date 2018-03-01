---
title: "WAIT_OPTION 枚举"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 143c191592efe8cfea8049f0dd5dc05a5bd4192f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="waitoption-enumeration"></a>WAIT_OPTION 枚举
包含值，用于指示是否公共语言运行时 (CLR) 块中请求的操作，应采取的措施主机。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|通知宿主任务应被唤醒，如果 CLR 调用[ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)方法。|  
|`WAIT_MSGPUMP`|通知主机，如果线程被阻止，它必须发送当前的操作系统线程上的消息。 运行时指定此值仅在上<xref:System.Threading.ApartmentState.STA>线程。|  
|`WAIT_NOTINDEADLOCK`|通知主机宿主无法中断指定的同步请求。 主机不能返回，即`HOST_E_DEADLOCK`。|  
  
## <a name="remarks"></a>备注  
 [Ihosttaskmanager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)和[ihosttaskmanager:: Switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)方法都执行此类型的参数。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
