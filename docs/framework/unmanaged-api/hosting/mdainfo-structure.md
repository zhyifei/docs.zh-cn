---
title: "MDAInfo 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: MDAInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: MDAInfo
helpviewer_keywords: MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53a999028f2677599598caf55e62f10721f61fe3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="mdainfo-structure"></a>MDAInfo 结构
提供有关的详细信息`Event_MDAFired`触发的托管调试助手 (MDA) 创建的事件。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`lpMDACaption`|当前的 MDA 的标题。 标题描述触发的失败的`Event_MDAFired`事件。|  
|`lpMDAMessage`|提供当前 MDA 的输出消息。|  
  
## <a name="remarks"></a>备注  
 托管调试助手 (Mda) 的运行时执行引擎中的调试辅助程序与公共语言运行时 (CLR) 来执行任务，例如标识无效的条件结合使用工作或转储有关的状态的其他信息引擎。 Mda 生成关于难以否则捕获的事件的 XML 消息。 它们是对调试托管和非托管代码之间的转换尤其有用。  
  
 激发事件触发的 MDA 创建时，运行时将执行以下步骤：  
  
-   如果主机未注册[IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)实例通过调用[iclroneventmanager:: Registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)接收通知的`Event_MDAFired`事件，运行时将继续其默认情况下，非托管的行为。  
  
-   如果主机已注册此事件的处理程序，运行时将进行检查以确定是否将调试器附加到进程。 如果是，运行时将中断调试器。 当调试器会继续时，它将调入主机。 如果未附加调试器，则运行时调用`IActionOnCLREvent::OnEvent`并将传递指向的指针`MDAInfo`实例作为`data`参数。  
  
 若要激活 Mda，并激活 MDA 时接收通知，可以选择主机。 这样，主机有机会将重写默认行为以及中止引发事件，以防止损坏的处理状态的托管的线程。 有关使用 Mda 的详细信息，请参阅[使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.idl  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载结构](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
