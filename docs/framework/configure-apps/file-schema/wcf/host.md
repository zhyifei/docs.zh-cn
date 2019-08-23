---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 21d53df12c2b2d703b771e2b9cb5ee87dafc410e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918712"
---
# <a name="host"></a>\<主机 >
指定服务主机的设置。  
  
 \<system.ServiceModel>  
\<services>  
\<service>  
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
|[\<baseAddresses>](baseaddresses.md)|`baseAddress` 元素的集合，指定服务主机所使用的基址。|  
|[\<timeOuts>](timeouts.md)|一个配置元素，指定为打开或关闭服务主机预留的时间间隔。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<service>](service.md)|指定 Windows Communication Foundation (WCF) 服务的设置。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [承载](../../../wcf/feature-details/hosting.md)
