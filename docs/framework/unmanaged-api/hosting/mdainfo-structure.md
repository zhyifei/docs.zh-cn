---
title: MDAInfo 结构
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
ms.openlocfilehash: 9a2f513d40d722f1b0aad823ac7c0d93bda5615f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123261"
---
# <a name="mdainfo-structure"></a>MDAInfo 结构
提供有关 `Event_MDAFired` 事件的详细信息，该事件可触发托管调试助手（MDA）的创建。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`lpMDACaption`|当前 MDA 的标题。 标题描述触发 `Event_MDAFired` 事件的故障类型。|  
|`lpMDAMessage`|当前 MDA 提供的输出消息。|  
  
## <a name="remarks"></a>备注  
 托管调试助手（Mda）是调试辅助工具，可与公共语言运行时（CLR）结合使用来执行任务，例如，在运行时执行引擎中标识无效条件或转储有关的状态的其他信息搜索引擎优化. Mda 生成的 XML 消息与其他难以捕获的事件有关。 它们对于调试托管代码和非托管代码之间的转换特别有用。  
  
 触发创建 MDA 的事件时，运行时将执行以下步骤：  
  
- 如果主机尚未通过调用 [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) 来注册 [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) `Event_MDAFired` 事件的通知，则运行时将继续默认的非托管行为。  
  
- 如果主机注册了此事件的处理程序，则运行时将进行检查以确定调试器是否已附加到进程。 如果为，则运行时会中断调试器。 调试器继续时，它会调入宿主。 如果未附加任何调试器，则运行时将调用 `IActionOnCLREvent::OnEvent`，并将一个指针作为 `data` 参数传递到 `MDAInfo` 实例。  
  
 宿主可以选择激活 mda，并在激活 MDA 时获得通知。 这使宿主有机会覆盖默认行为，并中止引发事件的托管线程，以防止其损坏进程状态。 有关使用 Mda 的详细信息，请参阅[使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 MSCorEE.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [承载结构](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
