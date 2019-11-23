---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 7fa72d233d6489ab6a2c534f69c66a55a22d0f59
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429828"
---
# <a name="udpbinding"></a><span data-ttu-id="9e778-101">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="9e778-101">\<udpBinding></span></span>
<span data-ttu-id="9e778-102">用于配置 <xref:System.ServiceModel.UdpBinding> 绑定的配置元素。</span><span class="sxs-lookup"><span data-stu-id="9e778-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
<span data-ttu-id="9e778-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9e778-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9e778-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9e778-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9e778-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9e778-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9e778-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<udpBinding>**</span><span class="sxs-lookup"><span data-stu-id="9e778-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e778-107">语法</span><span class="sxs-lookup"><span data-stu-id="9e778-107">Syntax</span></span>  
  
```xml  
<udpBinding>
  <binding closeTimeout="TimeSpan"
           duplicateMessageHistoryLength="Integer"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxPendingMessagesTotalSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetransmitCount="Integer"
           multicastInterfaceId="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           timeToLive="TimeSpan">
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e778-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9e778-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9e778-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9e778-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e778-110">特性</span><span class="sxs-lookup"><span data-stu-id="9e778-110">Attributes</span></span>  
  
|<span data-ttu-id="9e778-111">特性</span><span class="sxs-lookup"><span data-stu-id="9e778-111">Attribute</span></span>|<span data-ttu-id="9e778-112">描述</span><span class="sxs-lookup"><span data-stu-id="9e778-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="9e778-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="9e778-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="9e778-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="9e778-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9e778-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="9e778-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="9e778-116">一个整数值，指定重复消息历史记录长度。</span><span class="sxs-lookup"><span data-stu-id="9e778-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="9e778-117">一个整数值，指定为从通道接收消息的消息缓冲区管理器分配并供其使用的最大内存量。</span><span class="sxs-lookup"><span data-stu-id="9e778-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="9e778-118">默认值为 524288 (0x80000) 字节。</span><span class="sxs-lookup"><span data-stu-id="9e778-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="9e778-119">一个整数值，指定为采用此绑定配置的终结点处理消息时存储消息的缓冲区的最大大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="9e778-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="9e778-120">默认值为 65,536 字节。</span><span class="sxs-lookup"><span data-stu-id="9e778-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="9e778-121">一个整数值，指定已经接收但尚未从单个通道实例的输入队列中移除的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="9e778-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="9e778-122">一个正整数，定义在采用此绑定配置的通道上可以接收的消息的最大消息大小（字节），包括消息头。</span><span class="sxs-lookup"><span data-stu-id="9e778-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="9e778-123">如果消息对于接收方而言太大，则发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="9e778-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="9e778-124">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="9e778-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="9e778-125">默认值为 65,536 字节。</span><span class="sxs-lookup"><span data-stu-id="9e778-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="9e778-126">一个整数值，指定最大转发消息数。</span><span class="sxs-lookup"><span data-stu-id="9e778-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="9e778-127">一个整数值，指定多播接口 ID。</span><span class="sxs-lookup"><span data-stu-id="9e778-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="9e778-128">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="9e778-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="9e778-129">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9e778-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="9e778-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="9e778-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9e778-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9e778-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="9e778-132">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="9e778-132">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9e778-133">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="9e778-133">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9e778-134">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="9e778-134">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="9e778-135">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="9e778-135">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9e778-136">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="9e778-136">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9e778-137">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="9e778-137">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="9e778-138">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="9e778-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9e778-139">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="9e778-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9e778-140">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="9e778-140">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="9e778-141">设置要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="9e778-141">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="9e778-142">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="9e778-142">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9e778-143">-   BigEndianUnicode: Unicode BigEndian encoding.</span><span class="sxs-lookup"><span data-stu-id="9e778-143">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="9e778-144">-   Unicode: 16-bit encoding.</span><span class="sxs-lookup"><span data-stu-id="9e778-144">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="9e778-145">-   UTF8: 8-bit encoding</span><span class="sxs-lookup"><span data-stu-id="9e778-145">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="9e778-146">默认值为 UTF8。</span><span class="sxs-lookup"><span data-stu-id="9e778-146">The default is UTF8.</span></span> <span data-ttu-id="9e778-147">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="9e778-147">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="9e778-148">一个时间范围值，指定绑定处于活动状态的时间。</span><span class="sxs-lookup"><span data-stu-id="9e778-148">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e778-149">子元素</span><span class="sxs-lookup"><span data-stu-id="9e778-149">Child Elements</span></span>  
  
|<span data-ttu-id="9e778-150">元素</span><span class="sxs-lookup"><span data-stu-id="9e778-150">Element</span></span>|<span data-ttu-id="9e778-151">描述</span><span class="sxs-lookup"><span data-stu-id="9e778-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e778-152">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9e778-152">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="9e778-153">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="9e778-153">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="9e778-154">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="9e778-154">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e778-155">父元素</span><span class="sxs-lookup"><span data-stu-id="9e778-155">Parent Elements</span></span>  
  
|<span data-ttu-id="9e778-156">元素</span><span class="sxs-lookup"><span data-stu-id="9e778-156">Element</span></span>|<span data-ttu-id="9e778-157">描述</span><span class="sxs-lookup"><span data-stu-id="9e778-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e778-158">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9e778-158">\<bindings></span></span>](bindings.md)|<span data-ttu-id="9e778-159">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="9e778-159">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e778-160">备注</span><span class="sxs-lookup"><span data-stu-id="9e778-160">Remarks</span></span>  
 <span data-ttu-id="9e778-161">UdpBinding 允许 WCF 服务通过 UDP 传输进行通信。</span><span class="sxs-lookup"><span data-stu-id="9e778-161">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="9e778-162">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span><span class="sxs-lookup"><span data-stu-id="9e778-162">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e778-163">示例</span><span class="sxs-lookup"><span data-stu-id="9e778-163">Example</span></span>  
 <span data-ttu-id="9e778-164">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span><span class="sxs-lookup"><span data-stu-id="9e778-164">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
            timeToLive="00:10:00">
    <readerQuotas />
  </binding>
</udpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="9e778-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e778-165">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="9e778-166">绑定</span><span class="sxs-lookup"><span data-stu-id="9e778-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9e778-167">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="9e778-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9e778-168">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="9e778-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9e778-169">\<binding></span><span class="sxs-lookup"><span data-stu-id="9e778-169">\<binding></span></span>](bindings.md)
