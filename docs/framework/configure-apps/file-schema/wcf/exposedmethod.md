---
title: '&lt;exposedMethod&gt;'
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 2a26ca90f6a66592c246cc9e5aef50cfa53b4bdd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltexposedmethodgt"></a>&lt;exposedMethod&gt;
表示一个在 COM+ 组件上的接口作为 Web 服务公开时公开的 COM+ 方法。  
  
 \<system.ServiceModel>  
\<comContracts>  
\<comContract >  
\<方法 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|一个字符串，包含在 COM+ 组件上的接口作为 Web 服务公开时公开的 COM+ 方法。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<exposedMethods >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|集合[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素。|  
  
## <a name="remarks"></a>备注  
 可以使用 COM+ 集成配置工具 (ComSvcConfig.exe) 来添加 COM 接口中的特定方法，使其出现在生成的服务协定中。  
  
 例如，可以使用以下命令将 `IFinances`.Financial 组件上的 `ItemOrders` COM 接口中的三个命名方法添加到生成的服务协定中。  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 时也运行 ComSvcConfig.exe，它会生成以下服务协定列出作为先前提到的方法[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素。  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 在服务初始化时，在运行时尝试通过反射和添加仅在列表中所包括的方法来生成服务协定[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素。 对于该服务协定中未包括的每个接口方法，都会产生一个跟踪。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>  
 <xref:System.ServiceModel.Configuration.ComMethodElement>  
 [\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [与 COM+ 应用程序集成](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [如何：配置 COM+ 服务设置](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
