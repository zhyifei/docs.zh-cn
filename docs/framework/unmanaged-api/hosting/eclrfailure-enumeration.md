---
title: "EClrFailure 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrFailure
helpviewer_keywords: EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94358fd0626fa17f1fd6d3c365aff79f89dde467
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="eclrfailure-enumeration"></a>EClrFailure 枚举
介绍一的系列主机可以对这些设置的策略操作的故障。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|代码的非关键区域中尝试分配资源 （例如线程、 的内存，块或锁定） 时出现的错误。|  
|`FAIL_CriticalResource`|代码的关键区域中尝试分配资源 （例如线程、 的内存，块或锁定） 时出现的错误。|  
|`FAIL_FatalRuntime`|公共语言运行时 (CLR) 不再能够在进程中运行托管的代码。 自此以后，对任何托管函数的调用返回 HOST_E_CLRNOTAVAILABLE HRESULT 的值。|  
|`FAIL_OrphanedLock`|线程未能释放锁后从返回<xref:System.AppDomain>对象。 主机不能设置此故障以使中止的线程。|  
|`FAIL_StackOverflow`|发生堆栈溢出。|  
|`FAIL_AccessViolation`|尝试读取或写入受保护的内存。 中不受支持[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。|  
|`FAIL_CodeContract`|代码协定出错。 请参阅[代码协定](../../../../docs/framework/debug-trace-profile/code-contracts.md)。|  
  
## <a name="remarks"></a>备注  
 请参阅[iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)方法有关的列表[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)主机可用于指定在故障条件的策略操作的值。 有关代码的关键和非关键区域的详细信息，请参阅[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetActionOnFailure 方法](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [IHostPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
