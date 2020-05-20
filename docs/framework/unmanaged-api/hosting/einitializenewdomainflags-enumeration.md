---
title: EInitializeNewDomainFlags 枚举
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616224"
---
# <a name="einitializenewdomainflags-enumeration"></a>EInitializeNewDomainFlags 枚举
使宿主能够向运行时提供有关应用程序域初始化的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|无标志。|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|通知公共语言运行时（CLR）宿主不会在方法中更改应用程序域的安全状态 <xref:System.AppDomainManager.InitializeNewDomain%2A> 。|  
  
## <a name="remarks"></a>备注  
 [ICLRDomainManager：： SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md)方法采用类型的参数 `EInitializeNewDomainFlags` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [承载枚举](hosting-enumerations.md)
- [SetAppDomainManagerType 方法](iclrdomainmanager-setappdomainmanagertype-method.md)
