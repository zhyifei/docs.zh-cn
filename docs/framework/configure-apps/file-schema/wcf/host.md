---
title: '&lt;主机&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: afa9d65223ab3a7730a55bc41ed98458707b32db
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145219"
---
# <a name="lthostgt"></a>&lt;主机&gt;
指定服务主机的设置。  
  
 \<system.ServiceModel>  
\<services>  
\<服务 >  
\<主机 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a>类型  
 `Type`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<baseAddresses >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|`baseAddress` 元素的集合，指定服务主机所使用的基址。|  
|[\<超时 >](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|一个配置元素，指定为打开或关闭服务主机预留的时间间隔。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<service>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|指定 Windows Communication Foundation (WCF) 服务的设置。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [承载](../../../../../docs/framework/wcf/feature-details/hosting.md)
