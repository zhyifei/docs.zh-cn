---
title: EHostBindingPolicyModifyFlags 枚举
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
ms.openlocfilehash: 256c362ae0aea51fea16ce799db243b105dee81a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616237"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>EHostBindingPolicyModifyFlags 枚举
允许主机指定公共语言运行时（CLR）在将策略修改从源程序集应用到目标程序集时应执行的重定向的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|指定 CLR 将源程序集的策略值链接到目标程序集的策略值。|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|指定 CLR 将执行默认操作。|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|指定 CLR 将目标程序集的策略值设置为最大值。|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|指定 CLR 将目标程序集的策略值替换为源程序集的策略值。|  
  
## <a name="remarks"></a>备注  
 [ICLRHostBindingPolicyManager：： ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)方法采用类型的参数 `EHostBindingPolicyModifyFlags` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRHostBindingPolicyManager 接口](iclrhostbindingpolicymanager-interface.md)
- [承载枚举](hosting-enumerations.md)
