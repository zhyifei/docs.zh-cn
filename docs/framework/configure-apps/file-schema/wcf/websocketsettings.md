---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 1101d021f3c7436c4f45a22a48e50f6d1553f753
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226867"
---
# <a name="websocketsettings"></a>\<webSocketSettings>
用来指定 Web Socket 设置的配置元素。  
  
\<system.ServiceModel>  
\<bindings>  
\<netHttpBinding>  
  
## <a name="syntax"></a>语法  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|createNotificationOnConnection|指定是否在连接时发送通知。|  
|disablePayloadMasking|指定是否禁用 Web Socket 掩码。|  
|keepAliveInterval|指定保持活动状态的间隔。|  
|maxPendingConnections|指定服务上等待调度的最大连接数。|  
|receiveBufferSize|指定接收缓冲区的大小。|  
|sendBufferSize|指定发送缓冲区的大小。|  
|subProtocol|指定 Web Socket 子协议。|  
|transportUsage|指定何时使用 Web Socket。|  
  
## <a name="transportusage-attribute"></a>transportUsage 特性  
  
|“值”|描述|  
|-----------|-----------------|  
|WhenDuplex|如果为双工协定，则使用 Web Socket 协议。|  
|Always|始终使用 Web Socket 协议，而不管协定类型。|  
|Never|永远不使用 Web Socket 协议。|  
  
### <a name="child-elements"></a>子元素  
 None  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|\<netHttpBinding>|指定 NetHttpBinding|  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用\<webSocketSettings > 元素。  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [绑定](../../../../../docs/framework/wcf/bindings.md)
- [配置系统提供的绑定](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [使用绑定配置服务和客户端](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
