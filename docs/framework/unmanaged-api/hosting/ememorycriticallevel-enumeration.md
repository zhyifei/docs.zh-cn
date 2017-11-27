---
title: "EMemoryCriticalLevel 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EMemoryCriticalLevel
api_location: mscoree.dll
api_type: COM
f1_keywords: EMemoryCriticalLevel
helpviewer_keywords: EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b15a6786cb99a64d441d7e05fb91cd8ff0f3af92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel 枚举
包含值，用于指示失败的影响，如果特定内存分配已请求但不能满足。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`eAppDomainCritical`|指示分配是在已请求该分配的域中执行托管的代码的关键。 如果无法分配内存，则 CLR 不能保证域仍可使用。 主机决定要执行不能满足分配时的操作。 它可以指示 CLR 中止`AppDomain`自动，或允许其通过方法调用上保持运行[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)。|  
|`eProcessCritical`|指示分配是至关重要的过程中的托管代码的执行。 此值在启动期间和运行时，使用终结器。 无法分配内存，CLR 不能在过程中由操作。 如果分配失败，将有效地禁用 CLR。 到 CLR 中的所有后续调用失败并 HOST_E_CLRNOTAVAILABLE。|  
|`eTaskCritical`|指示分配是运行已请求该分配的任务的关键。 如果无法分配内存，则 CLR 不能保证可以执行该任务。 出现故障，CLR 引发<xref:System.Threading.ThreadAbortException>物理操作系统线程上。|  
  
## <a name="remarks"></a>备注  
 在中定义的内存分配方法[IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)和[IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)接口需要此类型的参数。 根据失败的严重性，主机可以决定是否立即失败分配请求，或等待，直到可以满足。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRMemoryNotificationCallback 接口](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
