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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b18c89cee0c3f5088a9978e448a0d61de1b9848
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434240"
---
# <a name="eclroperation-enumeration"></a>EClrOperation 枚举
介绍一的组主机可以为其应用策略操作的操作。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|主机可以指定策略操作时所要采取<xref:System.AppDomain>卸载的非正常的 （强制） 方式。|  
|`OPR_AppDomainUnload`|主机可以指定策略操作时所要采取<xref:System.AppDomain>卸载。|  
|`OPR_FinalizerRun`|主机可以指定要执行终结器运行时策略操作。|  
|`OPR_ProcessExit`|主机可以指定在进程退出时要执行策略操作。|  
|`OPR_ThreadAbort`|主机可以指定策略中止线程时要执行操作。|  
|`OPR_ThreadRudeAbortInCriticalRegion`|主机可以指定策略强制中止线程代码的关键区域中发生时要执行操作。|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|主机可以指定策略强制中止线程代码的非关键区域中发生时所采取的操作。|  
  
## <a name="remarks"></a>备注  
 公共语言运行时 (CLR) 可靠性基础结构将区分中止和资源的代码和那些出现的代码的非关键区域中的关键区域中发生的分配失败。 这一区别设计用于允许宿主能够设置不同的策略，具体取决于代码中发生故障。  
  
 A*关键代码区域*是任何区域，CLR 不能保证该中止任务或无法完成请求的资源将影响当前的任务。 例如，如果任务持有的锁，并且收到一个 HRESULT，指示在发出内存分配请求时失败，它是不足仅仅是为了中止该任务以确保的稳定性<xref:System.AppDomain>，这是因为<xref:System.AppDomain>可能包含其他等待同一个锁的任务。 放弃当前任务可能会导致其他任务来停止响应 （或挂起）; 如果无限期。 在这种情况下，主机需要能够将卸载整个<xref:System.AppDomain>而不是风险潜在的不稳定性。  
  
 A*的代码的非关键区域*，另一方面，是，CLR 可以保证仅在其出错的任务，将会中止或失败影响的区域。  
  
 CLR 还区分中止正常和非正常 （强制） 中止。 一般情况下，正常中止使各种方法，以便中止任务，而强制中止则没有此类保证之前运行异常处理例程和终结器。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [EClrFailure 枚举](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [EPolicyAction 枚举](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
