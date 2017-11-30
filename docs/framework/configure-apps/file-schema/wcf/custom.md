---
title: "&lt;自定义&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5bccfc95313ae3ae4a692be2165dc694783a460e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomgt"></a>&lt;自定义&gt;
指定自定义对等解析程序服务的设置。  
  
\<system.serviceModel >  
\<绑定 >  
\<netPeerBinding >  
\<绑定 >  
\<冲突解决程序 >  
\<自定义 >  
  
## <a name="syntax"></a>语法  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`address`|一个 URI，指定承载自定义对等解析程序服务的对等节点的终结点地址。|  
|`resolverType`|一个字符串值，指定自定义对等解析程序服务的类型。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<标识 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|指定配置了此元素的自定义对等解析程序的标识。 此元素的类型为 <xref:System.ServiceModel.Configuration.IdentityElement>。|  
|[\<标头 >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|一个地址标头集合，可用于由自定义对等解析程序处理的 SOAP 消息。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<冲突解决程序 >](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|一个对等解析程序，可用于将对等网格 ID 解析为一组对等节点地址，这些地址表示参与网格的若干节点。|  
  
## <a name="remarks"></a>备注  
 此元素可定义自定义对等解析程序服务的基本设置，其中包括执行服务的对等解析程序的终结点地址和所有特定绑定设置。 有关创建自定义解析程序的详细信息，请参阅[向对等通道应用程序添加自定义解析程序](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [对等解析程序](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [将自定义解析程序添加到对等通道应用程序](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
