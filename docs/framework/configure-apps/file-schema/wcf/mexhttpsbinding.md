---
title: '&lt;mexHttpsBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4990965e364765628174f9e8765663c7a7df70d2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltmexhttpsbindinggt"></a>&lt;mexHttpsBinding&gt;
指定用于通过 HTTPS 进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。  
  
 \<系统。ServiceModel >  
\<绑定 >  
\<mexHttpsBinding >  
  
## <a name="syntax"></a>语法  
  
```xml  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`closeTimeout`|一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。 此值应大于或等于 <xref:System.TimeSpan.Zero>。 默认值为 00:01:00。|  
|`name`|一个包含绑定的配置名称的字符串。 因为此值用作绑定的标识，所以它应该是唯一的。 每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。 此外，在同一类型的绑定中，此名称是唯一的。 从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。 有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。|  
|`openTimeout`|一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。 此值应大于或等于 <xref:System.TimeSpan.Zero>。 默认值为 00:01:00。|  
|`receiveTimeout`|一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。 此值应大于或等于 <xref:System.TimeSpan.Zero>。 默认值为 00:10:00。|  
|`sendTimeout`|一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。 此值应大于或等于 <xref:System.TimeSpan.Zero>。 默认值为 00:01:00。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<绑定 >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|此元素包含标准绑定和自定义绑定的集合。|  
  
## <a name="remarks"></a>备注  
 此绑定实质上是支持使用证书的传输级安全性的 `WSHttpBinding` 绑定。 有关配置和使用此类的元数据终结点的详细信息，请参阅[如何： 配置自定义 Ws-metadata Exchange 绑定](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)，[如何： 检索元数据通过非 MEX 绑定](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)，与示例[自定义安全元数据终结点](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>  
 [如何： 使用配置文件为服务中发布元数据](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [发布和检索元数据通过自定义绑定](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [如何： 配置自定义 Ws-metadata Exchange 绑定](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [如何： 通过非 MEX 绑定的检索元数据](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)  
 [自定义安全元数据终结点](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 [元数据](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [配置系统提供的绑定](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [使用绑定来配置 Windows Communication Foundation 服务和客户端](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<绑定 >](../../../../../docs/framework/misc/binding.md)
