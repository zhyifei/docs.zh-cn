---
title: IAppDomainSetup 接口
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: 0fab64c31d4a73995c16d21767f4569f21c7df9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126874"
---
# <a name="iappdomainsetup-interface"></a>IAppDomainSetup 接口
提供属性，这些属性使宿主可以在调用[ICorRuntimeHost：： CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)方法来创建它之前配置 <xref:System.AppDomain?displayProperty=nameWithType> 类型。  
  
## <a name="properties"></a>属性  
  
|Property|描述|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|获取或设置包含该应用程序的目录的名称。|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|获取或设置应用程序的名称。|  
|<xref:System.AppDomainSetup.CachePath%2A>|获取或设置特定于应用程序的区域的名称，在该区域中对文件进行卷影复制。|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|获取或设置应用程序的配置文件的名称。|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|获取或设置用于存储和访问动态生成的文件的目录的名称。|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|获取或设置与此域关联的许可证文件的路径。|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|获取或设置目录列表，该列表与要探测其专用程序集的 <xref:System.AppDomainSetup.ApplicationBase%2A> 目录组合在一起。|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|获取或设置一个字符串值，该值包含或排除从应用程序的搜索路径 <xref:System.AppDomainSetup.ApplicationBase%2A>。|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|获取或设置目录的名称，这些目录包含要进行卷影复制的程序集。|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|获取或设置一个字符串，该字符串指示阴影复制是打开还是关闭。 有效值为 "true" 或 "false"。|  
  
## <a name="remarks"></a>备注  
 `IAppDomainSetup` 接口对应于 <xref:System.AppDomainSetup> 类型实现的托管 <xref:System.IAppDomainSetup> 接口。 有关其属性的详细说明，请参阅 <xref:System.IAppDomainSetup?displayProperty=nameWithType>。  
  
 `IAppDomainSetup` 表示可以在创建之前添加到 <xref:System.AppDomain> 实例的程序集绑定信息。 例如，主机可以设置 <xref:System.AppDomainSetup.ApplicationBase%2A> 属性来建立根目录，公共语言运行时（CLR）会探测托管程序集。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
