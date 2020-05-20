---
title: ICLRControl 接口
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: 54748fdeaf911591c21f4495335e54c777878f04
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615829"
---
# <a name="iclrcontrol-interface"></a>ICLRControl 接口
提供允许宿主获取公共语言运行时（CLR）的和配置方面的引用的方法。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetCLRManager 方法](iclrcontrol-getclrmanager-method.md)|获取一个接口指针，该指针指向主机可用于配置 CLR 的任何管理器类型的实例。|  
|[SetAppDomainManagerType 方法](iclrcontrol-setappdomainmanagertype-method.md)|将派生自的类型设置 <xref:System.AppDomainManager> 为应用程序域管理器的类型。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRAssemblyIdentityManager 接口](iclrassemblyidentitymanager-interface.md)
- [ICLRDebugManager 接口](iclrdebugmanager-interface.md)
- [ICLRGCManager 接口](iclrgcmanager-interface.md)
- [ICLRHostBindingPolicyManager 接口](iclrhostbindingpolicymanager-interface.md)
- [ICLRHostProtectionManager 接口](iclrhostprotectionmanager-interface.md)
- [ICLROnEventManager 接口](iclroneventmanager-interface.md)
- [ICLRPolicyManager 接口](iclrpolicymanager-interface.md)
- [IHostControl 接口](ihostcontrol-interface.md)
- [承载接口](hosting-interfaces.md)
