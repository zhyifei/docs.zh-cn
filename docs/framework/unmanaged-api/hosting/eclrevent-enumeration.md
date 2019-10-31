---
title: EClrEvent 枚举
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: ee749fd40f440e92f1d1b09c2ea5e7bdd51f1cbe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131136"
---
# <a name="eclrevent-enumeration"></a>EClrEvent 枚举
描述宿主可为其注册回调的公共语言运行时（CLR）事件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`Event_ClrDisabled`|指定 CLR 错误的严重错误。|  
|`Event_DomainUnload`|指定卸载特定 <xref:System.AppDomain>。|  
|`Event_MDAFired`|指定已生成托管调试助手（MDA）消息。|  
|`Event_StackOverflow`|指定发生堆栈溢出错误。|  
  
## <a name="remarks"></a>备注  
 宿主可以通过调用[ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)接口的方法，为 `EClrEvent` 所述的任何事件类型注册回调。 宿主通过调用[ICLRControl：： GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法获取指向此接口的指针。  
  
 可以多次引发 `Event_CLRDisabled` 和 `Event_DomainUnload` 事件，并从不同的线程引发 CLR 的卸载或禁用信号。  
  
 `Event_MDAFired` 事件将引发包含 MDA 消息的详细信息的[MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)实例的创建。 有关 Mda 的详细信息，请参阅[诊断托管调试助手的错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IActionOnCLREvent 接口](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
