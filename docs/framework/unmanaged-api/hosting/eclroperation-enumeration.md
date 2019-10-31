---
title: EClrOperation 枚举
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: 6becc44b061ff2baac63437b6a72375d1c3735b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131165"
---
# <a name="eclroperation-enumeration"></a>EClrOperation 枚举
描述主机可对其应用策略操作的一组操作。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|当以非正常（强制）方式卸载 <xref:System.AppDomain> 时，主机可以指定要执行的策略操作。|  
|`OPR_AppDomainUnload`|宿主可以指定卸载 <xref:System.AppDomain> 时要执行的策略操作。|  
|`OPR_FinalizerRun`|主机可以指定在终结器运行时执行的策略操作。|  
|`OPR_ProcessExit`|宿主可以指定在进程退出时要执行的策略操作。|  
|`OPR_ThreadAbort`|宿主可以指定在线程中止时要执行的策略操作。|  
|`OPR_ThreadRudeAbortInCriticalRegion`|宿主可以指定在关键代码区域发生强制线程中止时要执行的策略操作。|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|宿主可以指定在非关键代码区域发生强制线程中止时要执行的策略操作。|  
  
## <a name="remarks"></a>备注  
 公共语言运行时（CLR）可靠性基础结构区分关键代码区域发生的中止和资源分配失败，以及在非关键代码区域发生的失败。 这种区别旨在允许主机根据代码中发生故障的位置设置不同的策略。  
  
 *关键代码区域*是指 CLR 无法保证中止任务或未能完成资源请求的任何空间都将只影响当前任务。 例如，如果某个任务持有锁，并且收到一个 HRESULT，指示在发出内存分配请求时失败，则只需中止该任务以确保 <xref:System.AppDomain>的稳定性，因为 <xref:System.AppDomain> 可能包含其他任务正在等待相同的锁。 放弃当前任务可能会导致其他任务停止响应。 在这种情况下，主机需要能够卸载整个 <xref:System.AppDomain> 而不是风险潜在的不稳定。  
  
 另一方面，*非关键的代码区域*是一个区域，在此区域中，CLR 可以保证中止或失败只会影响发生错误的任务。  
  
 CLR 还可以区分正常和不正常（强制）中止。 通常情况下，正常或正常中止会使每个工作在中止任务之前运行异常处理例程和终结器，而强制中止则不会有这样的保证。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [EClrFailure 枚举](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EPolicyAction 枚举](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
