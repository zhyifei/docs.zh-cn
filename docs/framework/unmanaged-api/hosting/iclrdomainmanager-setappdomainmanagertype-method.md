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
ms.openlocfilehash: ea10f9b7d23d8ca6a94d05cac6e586b434c000d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType 方法
指定的类型，派生自<xref:System.AppDomainManager?displayProperty=nameWithType>类，用于初始化默认应用程序域的应用程序域管理器。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszAppDomainManagerAssembly`  
 [in]包含应用程序域管理器类型; 程序集的显示名称例如:"AdMgrExample，Version = 1.0.0.0，Culture = neutral，PublicKeyToken = 6856bccf150f00b3"。  
  
 `wszAppDomainManagerType`  
 [in]应用程序域管理器，包括命名空间的类型名称。  
  
 `dwInitializeDomainFlags`  
 [in]组合[EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)提供有关应用程序域管理器的信息的枚举值。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
  
## <a name="remarks"></a>备注  
 目前，唯一定义的值为`dwInitializeDomainFlags`是`eInitializeNewDomainFlags_NoSecurityChanges`，它指示公共语言运行时 (CLR) 的应用程序域管理器执行期间将不修改安全设置<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>方法。 这允许以优化的有条件的程序集加载的 CLR <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 特性。 如果此集的程序集的传递闭包很大，这可能导致在启动时间的重大进步。  
  
> [!IMPORTANT]
>  如果主机指定`eInitializeNewDomainFlags_NoSecurityChanges`对于应用程序域管理器，<xref:System.InvalidOperationException>如果尝试修改的应用程序域的安全，则引发。  
  
 调用[iclrcontrol:: Setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)方法等效于调用`ICLRDomainManager::SetAppDomainManagerType`与`eInitializeNewDomainFlags_None`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRDomainManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [EInitializeNewDomainFlags 枚举](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
