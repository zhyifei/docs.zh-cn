---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: e5f1d49e0e3bb5f52c5e18577d556d25539434a9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400165"
---
# <a name="namedpipetransport"></a>\<namedPipeTransport>
定义传输，使通道在被包括到自定义绑定中时使用命名管道来传输消息。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<namedPipeTransport >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|ChannelInitializationTimeout|获取或设置一个<xref:System.TimeSpan> ，它确定通道在断开连接前可处于初始化状态的最大时间。|  
|ConnectionBufferSize|获取或设置用于从客户端或服务传输网络上的序列化消息块的缓冲区大小。|  
|hostNameComparisonMode|获取或设置一个值，该值指示在对 URI 进行匹配时，是否使用主机名来访问服务。|  
|manualAddressing|获取或设置一个值，该值指示是否要求对消息进行手动寻址。|  
|maxBufferPoolSize|获取或设置传输使用的任何缓冲池的最大大小（以字节为单位）。|  
|maxBufferSize|获取或设置要使用的缓冲区的最大大小。 对于经过流处理的消息，该值最少应为以缓冲模式读取的消息头的最大可能大小。|  
|maxOutputDelay|获取或设置消息块或完整消息在发出之前可以在内存中保持缓冲的最大时间间隔。|  
|maxPendingAccepts|获取或设置服务在侦听器上等待处理到服务的传入连接的最大通道数。|  
|maxPendingConnections|获取或设置在服务上等待调度的最大连接数。|  
|maxReceivedMessageSize|获取和设置允许接收的最大消息大小（以字节为单位）。|  
|transferMode|获取或设置一个值，该值指示通过面向连接的传输对消息进行缓冲还是流处理。|  
|[\<connectionPoolSettings > \<namedPipeTransport >](connectionpoolsettings.md)|指定命名管道绑定的其他连接池设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<binding>](../../../misc/binding.md)|定义自定义绑定的所有绑定功能。|  
  
## <a name="remarks"></a>备注  
此传输使用“net.pipe://hostname/path”形式的 URI。 其他 URI 组件是可选的。  
  
`namedPipeTransport` 元素是创建实现命名管道传输协议的自定义绑定的起始点。 此传输用于计算机上的 WCF (Windows Communication Foundation) 到 WCF 的通信。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [传输](../../../wcf/feature-details/transports.md)
- [选择传输](../../../wcf/feature-details/choosing-a-transport.md)
- [绑定](../../../wcf/bindings.md)
- [扩展绑定](../../../wcf/extending/extending-bindings.md)
- [自定义绑定](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
