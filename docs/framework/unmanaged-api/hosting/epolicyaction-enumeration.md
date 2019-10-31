---
title: EPolicyAction 枚举
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138235"
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction 枚举
描述主机可为[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)描述的操作设置的策略操作以及[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)描述的故障。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`eAbortThread`|指定公共语言运行时（CLR）应正常中止线程。 正常中止包括尝试运行所有 `finally` 块、与线程中止相关的任何 `catch` 块和终结器。|  
|`eDisableRuntime`|指定 CLR 应进入禁用状态。 在受影响的进程中，不能再执行其他托管代码，并且阻止线程进入 CLR。|  
|`eExitProcess`|指定 CLR 应尝试正常退出进程，包括运行终结器并执行清理和日志记录操作。|  
|`eFastExitProcess`|指定 CLR 应立即退出进程，而无需运行终结器或执行清理和日志记录操作。 但是，通知将发送到调试器。|  
|`eNoAction`|指定不执行任何操作。|  
|`eRudeAbortThread`|指定 CLR 应执行强制的线程中止。 只会执行标记为 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 的 `catch` 和 `finally` 块。|  
|`eRudeExitProcess`|指定 CLR 应退出进程，而不运行终结器或日志记录操作。|  
|`eRudeUnloadAppDomain`|指定 CLR 应执行 <xref:System.AppDomain>的强制卸载。 仅执行标记为 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 的终结器。 同样，具有此 <xref:System.AppDomain> 在其堆栈中的所有线程都接收到 `ThreadAbortException`，但仅执行标记为 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 的 `catch` 和 `finally` 块。|  
|`eThrowException`|指定应引发适用于条件的异常，例如内存不足、缓冲区溢出，等等。|  
|`eUnloadAppDomain`|指定应卸载 <xref:System.AppDomain>。 CLR 尝试运行终结器。|  
  
## <a name="remarks"></a>备注  
 宿主通过调用[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)接口的方法来设置策略操作。 有关 "强制" 和 "正常中止" 的信息，请参阅[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)枚举。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [EClrFailure 枚举](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [ICLRPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
