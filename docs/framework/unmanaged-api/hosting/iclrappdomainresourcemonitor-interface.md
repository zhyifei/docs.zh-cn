---
title: ICLRAppDomainResourceMonitor 接口
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc2326c72c9a1c63c4740608e120ace5dc83ebee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434865"
---
# <a name="iclrappdomainresourcemonitor-interface"></a>ICLRAppDomainResourceMonitor 接口
提供检查应用程序域的内存和 CPU 使用率的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetCurrentAllocated 方法](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|获取用字节表示，已由应用程序域创建以来，不扣除已进行垃圾回收的内存的所有内存分配的总大小。|  
|[GetCurrentSurvived 方法](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|获取最后一个完整、 阻碍性垃圾回收后保留下来的、 由当前的应用程序域引用的字节数。|  
|[GetCurrentCpuTime 方法](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|获取自应用程序域创建以来在当前的应用程序域中，执行时使用的所有线程的总处理器时间。|  
  
## <a name="remarks"></a>备注  
 `ICLRAppDomainResourceMonitor`接口提供类似于以下托管属性的功能：  
  
-   <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [\<appDomainResourceMonitoring > 元素](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
 [应用程序域资源监视](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
