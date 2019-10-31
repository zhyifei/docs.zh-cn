---
title: IHostControl 接口
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 444a78705c61d5a53764f55185ef1a907830bd71
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195882"
---
# <a name="ihostcontrol-interface"></a>IHostControl 接口
提供用于配置程序集加载和确定宿主支持哪些宿主接口的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetHostManager 方法](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|获取一个接口指针，该指针指向具有指定 `IID`的接口的主机实现。|  
|[SetAppDomainManager 方法](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|通知宿主已创建应用程序域。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.AppDomainManager>
- [ICLRRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
