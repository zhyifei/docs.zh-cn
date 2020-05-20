---
title: ICLRHostBindingPolicyManager 接口
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 3cf2a945607bf85a51dbec35342ff5ac46878bca
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703564"
---
# <a name="iclrhostbindingpolicymanager-interface"></a>ICLRHostBindingPolicyManager 接口
为宿主提供方法，用于评估当前的绑定策略并传达指定程序集的策略更改。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[EvaluatePolicy 方法](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|代表主机计算绑定策略。|  
|[ModifyApplicationPolicy 方法](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|修改指定程序集的绑定策略，并创建该策略的新版本。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRAssemblyIdentityManager 接口](iclrassemblyidentitymanager-interface.md)
- [IHostAssemblyStore 接口](ihostassemblystore-interface.md)
- [承载接口](hosting-interfaces.md)
