---
title: ICLRDomainManager::SetAppDomainManagerType 方法
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b142f1a05036eddf44c69d8b7da95091dc8f445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963095"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType 方法
指定从<xref:System.AppDomainManager?displayProperty=nameWithType>类派生的、将用于初始化默认应用程序域的应用程序域管理器的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszAppDomainManagerAssembly`  
 中包含应用程序域管理器类型的程序集的显示名称;例如:"AdMgrExample, Version = 1.0.0.0, Culture = 中立, PublicKeyToken = 6856bccf150f00b3"。  
  
 `wszAppDomainManagerType`  
 中应用程序域管理器的类型名称, 包括命名空间。  
  
 `dwInitializeDomainFlags`  
 中[EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)枚举值的组合, 提供有关应用程序域管理器的信息。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
  
## <a name="remarks"></a>备注  
 目前, 的唯一定义的值`dwInitializeDomainFlags`为`eInitializeNewDomainFlags_NoSecurityChanges`, 它指示公共语言运行时 (CLR), 应用程序域管理器在执行<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>方法期间将不会修改安全设置。 这样, CLR 就可以优化具有条件<xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 属性的程序集的加载。 如果这组程序集的可传递闭包很大, 则这可能会显著提高启动时间。  
  
> [!IMPORTANT]
> 如果主机为应用`eInitializeNewDomainFlags_NoSecurityChanges`程序域管理器指定了<xref:System.InvalidOperationException> , 则如果尝试修改应用程序域的安全性, 则会引发。  
  
 调用[ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)方法等效于调用`ICLRDomainManager::SetAppDomainManagerType`。 `eInitializeNewDomainFlags_None`  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRDomainManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [EInitializeNewDomainFlags 枚举](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
