---
title: '&lt;udpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: e17919ead6d6f7656c39d18b0ce1817c18da524a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43740265"
---
# <a name="ltudpbindinggt"></a><span data-ttu-id="51a15-102">&lt;udpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="51a15-102">&lt;udpBinding&gt;</span></span>
<span data-ttu-id="51a15-103">用于配置 <xref:System.ServiceModel.UdpBinding> 绑定的配置元素。</span><span class="sxs-lookup"><span data-stu-id="51a15-103">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="51a15-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="51a15-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="51a15-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="51a15-105">\<bindings></span></span>  
<span data-ttu-id="51a15-106">\<udpBinding ></span><span class="sxs-lookup"><span data-stu-id="51a15-106">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51a15-107">语法</span><span class="sxs-lookup"><span data-stu-id="51a15-107">Syntax</span></span>  
  
```xml  
<udpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       duplicateMessageHistoryLength="Integer"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"       maxPendingMessagesTotalSize="Integer"  
       maxReceivedMessageSize="Integer"       maxRetransmitCount="Integer"  
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
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51a15-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="51a15-108">Attributes and Elements</span></span>  
 <span data-ttu-id="51a15-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="51a15-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51a15-110">特性</span><span class="sxs-lookup"><span data-stu-id="51a15-110">Attributes</span></span>  
  
|<span data-ttu-id="51a15-111">特性</span><span class="sxs-lookup"><span data-stu-id="51a15-111">Attribute</span></span>|<span data-ttu-id="51a15-112">描述</span><span class="sxs-lookup"><span data-stu-id="51a15-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="51a15-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="51a15-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="51a15-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="51a15-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51a15-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="51a15-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="51a15-116">一个整数值，指定重复消息历史记录长度。</span><span class="sxs-lookup"><span data-stu-id="51a15-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="51a15-117">一个整数值，指定为从通道接收消息的消息缓冲区管理器分配并供其使用的最大内存量。</span><span class="sxs-lookup"><span data-stu-id="51a15-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="51a15-118">默认值为 524288 (0x80000) 字节。</span><span class="sxs-lookup"><span data-stu-id="51a15-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="51a15-119">一个整数值，指定为采用此绑定配置的终结点处理消息时存储消息的缓冲区的最大大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="51a15-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="51a15-120">默认值为 65,536 字节。</span><span class="sxs-lookup"><span data-stu-id="51a15-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="51a15-121">一个整数值，指定已经接收但尚未从单个通道实例的输入队列中移除的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="51a15-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="51a15-122">一个正整数，定义在采用此绑定配置的通道上可以接收的消息的最大消息大小（字节），包括消息头。</span><span class="sxs-lookup"><span data-stu-id="51a15-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="51a15-123">如果消息对于接收方而言太大，则发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="51a15-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="51a15-124">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="51a15-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="51a15-125">默认值为 65,536 字节。</span><span class="sxs-lookup"><span data-stu-id="51a15-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="51a15-126">一个整数值，指定最大转发消息数。</span><span class="sxs-lookup"><span data-stu-id="51a15-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="51a15-127">一个整数值，指定多播接口 ID。</span><span class="sxs-lookup"><span data-stu-id="51a15-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="51a15-128">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="51a15-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="51a15-129">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="51a15-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="51a15-130">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="51a15-130">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="51a15-131">此外，在同一类型的绑定中，此名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="51a15-131">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="51a15-132">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="51a15-132">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="51a15-133">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="51a15-133">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="51a15-134">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="51a15-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="51a15-135">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="51a15-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51a15-136">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="51a15-136">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="51a15-137">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="51a15-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="51a15-138">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="51a15-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51a15-139">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="51a15-139">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="51a15-140">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="51a15-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="51a15-141">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="51a15-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51a15-142">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="51a15-142">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="51a15-143">设置要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="51a15-143">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="51a15-144">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="51a15-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="51a15-145">-BigEndianUnicode: Unicode BigEndian 编码。</span><span class="sxs-lookup"><span data-stu-id="51a15-145">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="51a15-146">Unicode: 16 位编码。</span><span class="sxs-lookup"><span data-stu-id="51a15-146">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="51a15-147">-UTF8: 8 位编码</span><span class="sxs-lookup"><span data-stu-id="51a15-147">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="51a15-148">默认值为 UTF8。</span><span class="sxs-lookup"><span data-stu-id="51a15-148">The default is UTF8.</span></span> <span data-ttu-id="51a15-149">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="51a15-149">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="51a15-150">一个时间范围值，指定绑定处于活动状态的时间。</span><span class="sxs-lookup"><span data-stu-id="51a15-150">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51a15-151">子元素</span><span class="sxs-lookup"><span data-stu-id="51a15-151">Child Elements</span></span>  
  
|<span data-ttu-id="51a15-152">元素</span><span class="sxs-lookup"><span data-stu-id="51a15-152">Element</span></span>|<span data-ttu-id="51a15-153">描述</span><span class="sxs-lookup"><span data-stu-id="51a15-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51a15-154">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="51a15-154">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="51a15-155">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="51a15-155">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="51a15-156">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="51a15-156">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51a15-157">父元素</span><span class="sxs-lookup"><span data-stu-id="51a15-157">Parent Elements</span></span>  
  
|<span data-ttu-id="51a15-158">元素</span><span class="sxs-lookup"><span data-stu-id="51a15-158">Element</span></span>|<span data-ttu-id="51a15-159">描述</span><span class="sxs-lookup"><span data-stu-id="51a15-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51a15-160">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="51a15-160">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="51a15-161">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="51a15-161">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51a15-162">备注</span><span class="sxs-lookup"><span data-stu-id="51a15-162">Remarks</span></span>  
 <span data-ttu-id="51a15-163">UdpBinding 允许 WCF 服务通过 UDP 传输进行通信。</span><span class="sxs-lookup"><span data-stu-id="51a15-163">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="51a15-164">它允许"发后不理"消息交换的客户端向服务发送一条消息并不期望收到回复。</span><span class="sxs-lookup"><span data-stu-id="51a15-164">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51a15-165">示例</span><span class="sxs-lookup"><span data-stu-id="51a15-165">Example</span></span>  
 <span data-ttu-id="51a15-166">下面的示例演示如何使用 <<xref:System.ServiceModel.UdpBinding>> 元素配置 `udpBinding`。</span><span class="sxs-lookup"><span data-stu-id="51a15-166">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51a15-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="51a15-167">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="51a15-168">绑定</span><span class="sxs-lookup"><span data-stu-id="51a15-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="51a15-169">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="51a15-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="51a15-170">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="51a15-170">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="51a15-171">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="51a15-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
