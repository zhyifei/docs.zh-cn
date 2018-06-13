---
title: EBindPolicyLevels 枚举
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1da1d368725ab0a2334080c1caa7d4e25f5f3bab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431118"
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels 枚举
提供一些标志以指定在哪个应用或修改的程序集策略级别。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|指定应在管理员级别应用策略。|  
|`ePolicyLevelApp`|指定应在应用程序级别应用策略。|  
|`ePolicyLevelHost`|指定应在主机级别上应用策略。|  
|`ePolicyLevelNone`|不指定任何策略级别标志。|  
|`ePolicyLevelPublisher`|指定应在发布服务器级别应用策略。|  
|`ePolicyLevelRetargetable`|指定策略应适用变量级别。|  
|`ePolicyPortability`|指定策略应支持的.NET Framework 程序集的实现之间的可移植性。 请参阅[ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)配置文件元素。|  
|`ePolicyUnifiedToCLR`|指定策略应统一到的公共语言运行时 (CLR)。|  
  
## <a name="remarks"></a>备注  
 此枚举传递给方法的[ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)接口来在应用程序策略中指定的更改。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRAssemblyIdentityManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
