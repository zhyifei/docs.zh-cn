---
title: "ICorRuntimeHost::CreateDomainEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomainEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 042befa2dd96ad9f6e6dd3069ba2c4aabcd146fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreatedomainex-method"></a>ICorRuntimeHost::CreateDomainEx 方法
创建应用程序域。 调用方会收到类型的接口指针<xref:System._AppDomain>，到类型的实例<xref:System.AppDomain?displayProperty=nameWithType>。 此方法允许调用方传递一个 IAppDomainSetup 实例，以便配置其他功能，则返回的<xref:System._AppDomain>实例。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pwzFriendlyName`  
 [in]一个可选参数，用于为域友好名称。 此友好名称，可以显示在用户界面，例如调试器以标识域。  
  
 `pSetup`  
 [in]类型的可选接口指针`IAppDomainSetup`，通过调用获取[icorruntimehost:: Createdomainsetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)方法。  
  
 `pIdentityArray`  
 [in]指向的指针的可选数组`IIdentity`表示映射通过安全策略，以建立权限集的证据的实例。 `IIdentity`可以通过调用获取对象[CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)方法。  
  
 `pAppDomain`  
 [out]类型的接口指针<xref:System._AppDomain>到实例<xref:System.AppDomain?displayProperty=nameWithType>可以用于进一步控制域。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该操作成功。|  
|S_FALSE|操作无法完成。|  
|E_FAIL|发生了未知的灾难性故障。 如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。 对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
  
## <a name="remarks"></a>备注  
 `CreateDomainEx`扩展的功能[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)通过允许调用方传入`IAppDomainSetup`实例与用于配置应用程序域的属性值。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** 1.0、 1.1  
  
## <a name="see-also"></a>另请参阅  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [CreateDomain 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)  
 [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
