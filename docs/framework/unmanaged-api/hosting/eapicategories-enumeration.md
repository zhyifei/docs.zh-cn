---
title: EApiCategories 枚举
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
ms.openlocfilehash: 0fd9409a5157e1013365c94f01631f130a76f54b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131216"
---
# <a name="eapicategories-enumeration"></a>EApiCategories 枚举
描述宿主可阻止在部分受信任代码中运行的功能类别。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`eAll`|指定阻止其他 `EApiCategories` 字段覆盖的所有托管类和成员在部分受信任的代码中运行。|  
|`eExternalProcessMgmt`|指定禁止在部分受信任的代码中运行外部进程的创建、操作和析构的托管类和成员。|  
|`eExternalThreading`|指定允许在部分受信任的代码中阻止创建、操作和销毁外部线程的托管类和成员。|  
|`eMayLeakOnAbort`|指定在部分受信任的代码中阻止在中止时可能泄漏内存的托管类型和成员。|  
|`eNoCategory`|指定禁止在部分受信任的代码中运行托管代码类别。|  
|`eSecurityInfrastructure`|指定禁止部分受信任的代码使用公共语言运行时（CLR）安全基础结构。|  
|`eSelfAffectingProcessMgmt`|指定在部分受信任的代码中阻止其功能影响托管进程的托管类和成员运行。|  
|`eSelfAffectingThreading`|指定在部分受信任的代码中阻止其功能影响托管进程中的线程的托管类和成员。|  
|`eSharedState`|指定阻止公开共享状态的托管类和成员在部分受信任的代码中运行。|  
|`eSynchronization`|指定允许用户代码持有锁的公共语言运行时类和成员阻止在部分受信任的代码中运行。|  
|`eUI`|指定在部分受信任的代码中阻止允许或要求人工交互的托管类和成员。|  
  
## <a name="remarks"></a>备注  
 [ICLRHostProtectionManager：： SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)方法使用 `EApiCategories`类型的参数。  
  
 `EApiCategories` 枚举和 `SetProtectedCategories` 方法与托管 <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> 类直接相关。 托管类与 <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> 枚举一起使用，其值直接对应于 `EApiCategories` 值，用于标记公开与 `EApiCategories`所述的类别对应的功能的托管类型和成员。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRHostProtectionManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
