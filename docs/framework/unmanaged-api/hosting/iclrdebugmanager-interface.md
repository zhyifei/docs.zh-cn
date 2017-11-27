---
title: "ICLRDebugManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager
helpviewer_keywords: ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e537b955524f2721868ddf5da9fccf68f9d4efd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager 接口
提供使主机可将一组任务标识符和友好名称与相关联的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[BeginConnection 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|建立新连接在主机和调试器要与任务关联的友好名称标识符与之间。|  
|[EndConnection 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|删除的任务列表和标识符和友好名称之间的关联。|  
|[GetDacl 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|未实现此方法。|  
|[IsDebuggerAttached 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|获取一个值，它指示调试器是否已附加到进程。|  
|[SetConnectionTasks 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|将相关联的列表[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)标识符并具有友好名称的实例。|  
|[SetDacl 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|未实现此方法。|  
|[SetSymbolReadingPolicy 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|设置用于读取程序数据库 (PDB) 文件的策略。 策略将确定调用堆栈中是否包括行号和文件有关的信息。|  
  
## <a name="remarks"></a>备注  
 在调试方案中，宿主可能需要对任务进行分组根据其自己的编程逻辑。 例如，分组将允许开发人员以查看开发人员 Api，而不是在进程中运行的每项任务所需的任务。 `ICLRDebugManager`允许宿主实现这种分组。  
  
> [!IMPORTANT]
>  三个`ICLRDebugManager`方法， `BeginConnection`，`SetConnectionTasks`和`EndConnection`，依赖于彼此。 在给定的顺序，以便按预期方式工作，必须调用它们。  
  
 分组的标识符和主机分配给分组的友好名称具有对公共语言运行时 (CLR) 没有意义。 CLR 仅将信息传递给该调试器。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
