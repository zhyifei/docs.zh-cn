---
title: EClrUnhandledException 枚举
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: 63b07dda2293d3e05bd3c8fcdc45f20a498ea54c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616302"
---
# <a name="eclrunhandledexception-enumeration"></a>EClrUnhandledException 枚举
介绍用于管理用户代码中未经处理的异常的可用选项。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|指定发生默认行为。 进程已被破坏。|  
|`eHostDeterminedPolicy`|指定公共语言运行时（CLR）忽略未经处理的异常，并允许主机确定任何进一步的操作。|  
  
## <a name="remarks"></a>备注  
 若要指定 CLR 的行为类似于早期版本，请使用 `eHostDeterminedPolicy` 成员。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [EClrFailure 枚举](eclrfailure-enumeration.md)
- [EClrOperation 枚举](eclroperation-enumeration.md)
- [ICLRPolicyManager 接口](iclrpolicymanager-interface.md)
- [SetUnhandledExceptionPolicy 方法](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [IHostPolicyManager 接口](ihostpolicymanager-interface.md)
- [承载枚举](hosting-enumerations.md)
