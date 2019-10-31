---
title: ICLRDebugManager 接口
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
ms.openlocfilehash: 008143c608cd19bee9dd115e97620906fb5b93b9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129411"
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager 接口
提供允许主机将一组任务与标识符和友好名称关联的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[BeginConnection 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|在宿主和调试器之间建立新的连接，以将任务与标识符和友好名称关联起来。|  
|[EndConnection 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|删除任务列表与标识符和友好名称之间的关联。|  
|[GetDacl 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|未实现此方法。|  
|[IsDebuggerAttached 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|获取一个值，它指示调试器是否已附加到进程。|  
|[SetConnectionTasks 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|将[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例列表与标识符和友好名称关联。|  
|[SetDacl 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|未实现此方法。|  
|[SetSymbolReadingPolicy 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|设置用于读取程序数据库（PDB）文件的策略。 策略确定有关行号和文件的信息是否包含在调用堆栈中。|  
  
## <a name="remarks"></a>备注  
 在调试方案中，主机可能需要根据任务自己的编程逻辑对任务进行分组。 例如，分组允许开发人员仅查看开发人员的 Api 所需的任务，而不是查看在进程中运行的每个任务。 `ICLRDebugManager` 允许主机实现这种分组。  
  
> [!IMPORTANT]
> 三个 `ICLRDebugManager` 方法（`BeginConnection`、`SetConnectionTasks` 和 `EndConnection`）相互依赖。 必须按给定顺序调用它们才能按预期方式工作。  
  
 对于公共语言运行时（CLR），分组以及宿主分配给分组的标识符和友好名称没有任何意义。 CLR 只会将信息传递到调试器。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
