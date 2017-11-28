---
title: "EApiCategories 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EApiCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: EApiCategories
helpviewer_keywords: EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eaff0133020fe84e58f8a130bffc8ddc2a55a19d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="eapicategories-enumeration"></a>EApiCategories 枚举
描述了主机可以阻止其运行部分受信任代码中的功能的类别。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`eAll`|指定所有托管类和成员均覆盖由其他`EApiCategories`字段无法在部分受信任的代码中运行。|  
|`eExternalProcessMgmt`|指定托管的类和成员允许创建、 操作以及外部进程析构禁止在部分受信任的代码中运行。|  
|`eExternalThreading`|指定托管的类和成员允许创建、 操作以及销毁外部线程的阻止在部分受信任的代码中运行。|  
|`eMayLeakOnAbort`|指定托管的类型和成员无法可能泄漏内存中止禁止在部分受信任的代码中运行。|  
|`eNoCategory`|指定阻止在部分受信任的代码中运行任何托管的代码类别。|  
|`eSecurityInfrastructure`|指定阻止被部分受信任的代码所使用公共语言运行时 (CLR) 安全基础结构。|  
|`eSelfAffectingProcessMgmt`|指定托管的类和成员其功能可能会影响托管的进程禁止在部分受信任的代码中运行。|  
|`eSelfAffectingThreading`|指定托管的类和成员其功能可能会影响托管的进程中的线程禁止在部分受信任的代码中运行。|  
|`eSharedState`|指定托管的类和公开共享的状态的成员禁止在部分受信任的代码中运行。|  
|`eSynchronization`|指定公共语言运行时类和成员，允许用户代码持有的锁禁止在部分受信任的代码中运行。|  
|`eUI`|指定托管的类和成员，允许，或是需要人工交互禁止在部分受信任的代码中运行。|  
  
## <a name="remarks"></a>备注  
 [Iclrhostprotectionmanager:: Setprotectedcategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)方法采用一个参数类型`EApiCategories`。  
  
 `EApiCategories`枚举和`SetProtectedCategories`方法直接相关于托管<xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType>类。 托管的类用于<xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType>枚举，其值直接对应`EApiCategories`值，来标记托管的类型和公开对应于所描述的类别的功能的成员`EApiCategories`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRHostProtectionManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
