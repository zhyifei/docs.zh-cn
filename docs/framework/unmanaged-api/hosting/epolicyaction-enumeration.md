---
title: "EPolicyAction 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EPolicyAction
api_location: mscoree.dll
api_type: COM
f1_keywords: EPolicyAction
helpviewer_keywords: EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5de55d46eead37962fad7d7c1c5bd1766e772fe8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction 枚举
描述了主机可以为所描述的操作设置的策略操作[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)和所描述的失败[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`eAbortThread`|指定公共语言运行时 (CLR) 应正常中止此线程。 正常中止包括： 尝试运行所有`finally`阻止任何`catch`块与线程中止和终结器。|  
|`eDisableRuntime`|指定 CLR 应输入禁用的状态。 没有任何进一步在受影响的过程中，执行托管的代码和线程被阻止进入 CLR。|  
|`eExitProcess`|指定 CLR 应尝试过程中，包括运行终结器和执行清理和日志记录操作的正常退出。|  
|`eFastExitProcess`|指定的 CLR 应进程立即退出，无需运行终结器或执行清理和日志记录操作。 但要通知将发送到调试器。|  
|`eNoAction`|指定应执行任何操作。|  
|`eRudeAbortThread`|指定 CLR 应执行原始线程中止。 只有`catch`和`finally`块标记为<xref:System.EnterpriseServices.MustRunInClientContextAttribute>执行。|  
|`eRudeExitProcess`|指定 CLR 应退出无需运行终结器或日志记录操作的过程。|  
|`eRudeUnloadAppDomain`|指定 CLR 应执行强制卸载<xref:System.AppDomain>。 唯一的终结器标记为<xref:System.EnterpriseServices.MustRunInClientContextAttribute>执行。 同样，所有线程与此<xref:System.AppDomain>其堆栈中接收`ThreadAbortException`，但只有`catch`和`finally`块标记为<xref:System.EnterpriseServices.MustRunInClientContextAttribute>执行。|  
|`eThrowException`|指定应引发相应于该条件，如内存不足，缓冲区溢出等，异常。|  
|`eUnloadAppDomain`|指定<xref:System.AppDomain>将其卸载。 CLR 尝试运行终结器。|  
  
## <a name="remarks"></a>备注  
 主机通过调用的方法设置的策略操作[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)接口。 有关强制和正常中止的信息，请参阅[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)枚举。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [EClrFailure 枚举](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [ICLRPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
