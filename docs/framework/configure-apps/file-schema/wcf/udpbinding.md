---
title: "&lt;udpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;udpBinding&gt;
用于配置 <xref:System.ServiceModel.UdpBinding> 绑定的配置元素。  
  
## 语法  
  
```  
  
<udpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       duplicateMessageHistoryLength=”Integer"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"  
       maxPendingMessagesTotalSize=”Integer”  
       maxReceivedMessageSize="Integer"  
       maxRetransmitCount=”Integer”  
       multicastInterfaceId="Integer"  
              name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
       textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
       timeToLive="TimeSpan">  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"      
            maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## 特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### 特性  
  
|特性|描述|  
|--------|--------|  
|`closeTimeout`|一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。  此值应大于或等于 <xref:System.TimeSpan.Zero>。  默认值为 00:01:00。|  
|`duplicateMessageHistoryLength`|一个整数值，指定重复消息历史记录长度。|  
|`maxBufferPoolSize`|一个整数值，指定为从通道接收消息的消息缓冲区管理器分配并供其使用的最大内存量。  默认值为 524288 \(0x80000\) 字节。|  
|`maxBufferSize`|一个整数值，指定为采用此绑定配置的终结点处理消息时存储消息的缓冲区的最大大小（字节）。  默认值为 65,536 字节。|  
|`maxPendingMessagesTotalSize`|一个整数值，指定已经接收但尚未从单个通道实例的输入队列中移除的最大消息数。|  
|`maxReceivedMessageSize`|一个正整数，定义在采用此绑定配置的通道上可以接收的消息的最大消息大小（字节），包括消息头。  如果消息对于接收方而言太大，则发送方将收到 SOAP 错误。  接收方将删除该消息，并在跟踪日志中创建事件项。  默认值为 65,536 字节。|  
|`maxRetransmitCount`|一个整数值，指定最大转发消息数。|  
|`multicastInterfaceId`|一个整数值，指定多播接口 ID。|  
|`name`|一个包含绑定的配置名称的字符串。  因为此值用作绑定的标识，所以它应该是唯一的。  每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。  此外，在同一类型的绑定中，此名称是唯一的。  从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。  有关默认配置以及无名称绑定和行为的更多信息，请参见[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和 [WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。|  
|`openTimeout`|一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。  此值应大于或等于 <xref:System.TimeSpan.Zero>。  默认值为 00:01:00。|  
|`receiveTimeout`|一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。  此值应大于或等于 <xref:System.TimeSpan.Zero>。  默认值为 00:10:00。|  
|`sendTimeout`|一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。  此值应大于或等于 <xref:System.TimeSpan.Zero>。  默认值为 00:01:00。|  
|`textEncoding`|设置要用来在绑定上发出消息的字符集编码。  包括以下有效值：<br /><br /> -   BigEndianUnicode：Unicode BigEndian 编码。<br />-   Unicode：16 位编码。<br />-   UTF8：8 位编码<br /><br /> 默认值为 UTF8。  此属性的类型为 <xref:System.Text.Encoding>。|  
|`timeToLive`|一个时间范围值，指定绑定处于活动状态的时间。|  
  
### 子元素  
  
|元素|描述|  
|--------|--------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。  此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。|  
  
### 父元素  
  
|元素|描述|  
|--------|--------|  
|[\<绑定\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|此元素包含标准绑定和自定义绑定的集合。|  
  
## 备注  
 UdpBinding 允许 WCF 服务通过 UDP 传输进行通信。  它允许“发后不理”消息交换，即客户端向服务发送一条消息且不期望收到回复。  
  
## 示例  
 下面的示例演示如何使用 \<`udpBinding`\> 元素配置 <xref:System.ServiceModel.UdpBinding>。  
  
```xml  
<udpBinding>  
        <binding  closeTimeout="00:10:00"  
                   duplicateMessageHistoryLength="100"  
                   maxBufferPoolSize="100"  
                   maxPendingMessagesTotalSize="100000"  
                   maxReceivedMessageSize="65536"  
                    maxRetransmitCount="10"  
                   multicastInterfaceId="00000"  
                   name="myUdpBinding"  
                   openTimeout="00:10:00"  
                   receiveTimeout="00:10:00"  
                   sendTimeout="00:10:00"  
                   textEncoding="utf-8"  
                   timeToLive="00:10:00"  
          <readerQuotas/>   
        </binding>  
      </udpBinding>  
```  
  
## 请参阅  
 <xref:System.ServiceModel.Channels.Binding>   
 <xref:System.ServiceModel.Channels.BindingElement>   
 <xref:System.ServiceModel.BasicHttpBinding>   
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>   
 [绑定](../../../../../docs/framework/wcf/bindings.md)   
 [配置系统提供的绑定](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/zh-cn/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<绑定\>](../../../../../docs/framework/misc/binding.md)