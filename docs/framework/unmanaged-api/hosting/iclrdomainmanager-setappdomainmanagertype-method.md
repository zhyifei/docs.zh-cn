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
ms.openlocfilehash: 5c61e2e1208cec0bda1492964a8d02bd71f5a1c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129322"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType 方法
指定从应用程序域管理器的 <xref:System.AppDomainManager?displayProperty=nameWithType> 类派生的类型，将用于初始化默认应用程序域。  
  
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
 中包含应用程序域管理器类型的程序集的显示名称;例如： "AdMgrExample，Version = 1.0.0.0，Culture = 中立，PublicKeyToken = 6856bccf150f00b3"。  
  
 `wszAppDomainManagerType`  
 中应用程序域管理器的类型名称，包括命名空间。  
  
 `dwInitializeDomainFlags`  
 中[EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)枚举值的组合，提供有关应用程序域管理器的信息。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
  
## <a name="remarks"></a>备注  
 目前，`dwInitializeDomainFlags` 的唯一定义的值是 `eInitializeNewDomainFlags_NoSecurityChanges`，它告知公共语言运行时（CLR）应用程序域管理器在执行 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 方法期间将不会修改安全设置。 这样，CLR 就可以优化具有条件 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> （APTCA）特性的程序集的加载。 如果这组程序集的可传递闭包很大，则这可能会显著提高启动时间。  
  
> [!IMPORTANT]
> 如果主机指定应用程序域管理器的 `eInitializeNewDomainFlags_NoSecurityChanges`，则如果尝试修改应用程序域的安全性，则会引发 <xref:System.InvalidOperationException>。  
  
 调用[ICLRControl：： SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)方法等效于调用具有 `eInitializeNewDomainFlags_None`的 `ICLRDomainManager::SetAppDomainManagerType`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRDomainManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [EInitializeNewDomainFlags 枚举](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
