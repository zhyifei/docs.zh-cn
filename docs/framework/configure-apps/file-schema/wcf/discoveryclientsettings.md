---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 2783796166d56be3d4983ab09a60d62491699fe3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925867"
---
# <a name="discoveryclientsettings"></a>\<discoveryClientSettings>
包含应用程序以客户端形式参与服务发现过程所需的设置。  
  
\<system.ServiceModel>  
\<standardEndpoints>  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|discoveryEndpoint|一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。 可以将条件分组为搜索条件 (指定要查找的服务) 和查找终止条件 (搜索应持续的时间长度)。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|定义一个标准终结点，应用程序通过利用该终结点包含的信息，能够充当可在运行时动态查找终结点地址的客户端程序。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
