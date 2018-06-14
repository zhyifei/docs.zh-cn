---
title: ICorRuntimeHost 接口
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: facc756061e7eb381abecc544ca4b15bfdde6343
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440042"
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost 接口
提供使主机能够启动和停止公共语言运行时 (CLR) 显式创建和配置应用程序域，以访问默认域，以及枚举进程中运行的所有域的方法。  
  
 在.NET Framework 2.0 版中，此接口被取代[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CloseEnum 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|将域枚举数重置回域列表的开头。|  
|[CreateDomain 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|创建应用程序域。 调用方会收到类型的接口指针<xref:System._AppDomain>到类型的实例<xref:System.AppDomain?displayProperty=nameWithType>。|  
|[CreateDomainEx 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|创建应用程序域。 此方法允许调用方传递一个 IAppDomainSetup 实例，以便配置其他功能，则返回的<xref:System._AppDomain>实例。|  
|[CreateDomainSetup 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|获取类型的接口指针`IAppDomainSetup`到<xref:System.AppDomainSetup>实例。 `IAppDomainSetup` 提供用于配置应用程序域的方面，它将在创建之前方法。|  
|[CreateEvidence 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|获取类型的接口指针<xref:System.Security.Principal.IIdentity>，这样，主机可以在创建安全证据要传递给[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)或[CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)。|  
|[CreateLogicalThreadState 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|请勿使用。|  
|[CurrentDomain 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|获取类型的接口指针<xref:System._AppDomain>表示加载到当前线程上的域。|  
|[DeleteLogicalThreadState 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|请勿使用。|  
|[EnumDomains 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|域当前进程中获取一个枚举器。|  
|[GetConfiguration 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|获取允许宿主指定 CLR 的回调配置的对象。|  
|[GetDefaultDomain 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|获取类型的接口指针<xref:System._AppDomain>，它表示当前进程的默认域。|  
|[LocksHeldByLogicalThread 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|请勿使用。|  
|[MapFile 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|将指定的文件映射到内存中。 此方法已过时。|  
|[NextDomain 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|枚举中的下一个域中获取的接口指针。|  
|[Start 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|启动 CLR。|  
|[Stop 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|停止执行当前进程的运行时中的代码。|  
|[SwitchInLogicalThreadState 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|请勿使用。|  
|[SwitchOutLogicalThreadState 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|请勿使用。|  
|[UnloadDomain 方法](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|卸载指定的应用程序域中从当前进程。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** 1.0、 1.1  
  
## <a name="see-also"></a>请参阅  
 <xref:System.AppDomain>  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [运行时主机](http://msdn.microsoft.com/library/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost 组件类](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
