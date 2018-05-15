---
title: '&lt;netHttpsBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ff122116-6042-4792-9f21-275b4f97a105
ms.openlocfilehash: fb279321cccc325700ac18697d484da20c685c9d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltnethttpsbindinggt"></a><span data-ttu-id="91275-102">&lt;netHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="91275-102">&lt;netHttpsBinding&gt;</span></span>
<span data-ttu-id="91275-103">表示 Windows Communication Foundation (WCF) 服务可用于配置和公开能够通过 HTTPS 进行通信的终结点的绑定。</span><span class="sxs-lookup"><span data-stu-id="91275-103">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTPS.</span></span> <span data-ttu-id="91275-104">如果用于双工协定，将使用 Web Sockets，否则将使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="91275-104">When used with a duplex contract, Web Sockets will be used, otherwise HTTPS will be used.</span></span>  
  
 <span data-ttu-id="91275-105">根元素</span><span class="sxs-lookup"><span data-stu-id="91275-105">Root Element</span></span>  
<span data-ttu-id="91275-106">下一个元素</span><span class="sxs-lookup"><span data-stu-id="91275-106">Next Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91275-107">语法</span><span class="sxs-lookup"><span data-stu-id="91275-107">Syntax</span></span>  

```xml
<netHttpsBinding>  
  <binding allowCookies="Boolean"  
           bypassProxyOnLocal="Boolean"  
           closeTimeout="TimeSpan"   
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
           maxBufferPoolSize="Integer"  
           maxBufferSize="Integer"  
           maxReceivedMessageSize="Integer"  
           messageEncoding="Binary/Text/Mtom"  
           name="string"   
           openTimeout="TimeSpan"   
           proxyAddress="URI"  
           receiveTimeout="TimeSpan"  
           sendTimeout="TimeSpan"  
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">  
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"  
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"  
                 realm="string" />  
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" 
               clientCredentialType="UserName/Certificate"/>  
    </security>  
    <readerQuotas maxArrayLength="Integer" 
                  maxBytesPerRead="Integer" 
                  maxDepth="Integer" 
                  maxNameTableCharCount="Integer" 
                  maxStringContentLength="Integer" />  
  </binding>  
</netHttpsBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="91275-108">类型</span><span class="sxs-lookup"><span data-stu-id="91275-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91275-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="91275-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91275-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="91275-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91275-111">特性</span><span class="sxs-lookup"><span data-stu-id="91275-111">Attributes</span></span>  
  
|<span data-ttu-id="91275-112">特性</span><span class="sxs-lookup"><span data-stu-id="91275-112">Attribute</span></span>|<span data-ttu-id="91275-113">描述</span><span class="sxs-lookup"><span data-stu-id="91275-113">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="91275-114">一个布尔值，指示客户端是否接受 Cookie 并在今后的请求中传播这些 Cookie。</span><span class="sxs-lookup"><span data-stu-id="91275-114">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="91275-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="91275-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="91275-116">在与使用 Cookie 的 ASMX Web 服务进行交互时，可以使用此属性。</span><span class="sxs-lookup"><span data-stu-id="91275-116">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="91275-117">通过这种方式，可以确保从服务器返回的 Cookie 自动复制到客户端今后对该服务的所有请求。</span><span class="sxs-lookup"><span data-stu-id="91275-117">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="91275-118">一个布尔值，指示是否对本地地址不使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="91275-118">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="91275-119">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="91275-119">The default is `false`.</span></span><br /><br /> <span data-ttu-id="91275-120">如果 Internet 资源具有本地地址，则该资源是本地资源。</span><span class="sxs-lookup"><span data-stu-id="91275-120">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="91275-121">本地地址是指位于同一台计算机、 本地 LAN 或 intranet 上和标识，语法上通过省略句点 （.） 如 Uri"http://webserver/"和"http://localhost/"。</span><span class="sxs-lookup"><span data-stu-id="91275-121">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="91275-122">通过设置此属性，可以确定在访问本地资源时，采用 BasicHttpBinding 配置的终结点是否使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="91275-122">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="91275-123">如果此属性为 `true`，则对本地 Internet 资源的请求不使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="91275-123">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="91275-124">当此属性设置为 `true` 时，如果希望客户端在与同一台计算机上的服务通话时使用代理，请使用主机名称（而非 localhost）。</span><span class="sxs-lookup"><span data-stu-id="91275-124">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="91275-125">当此属性为 `false` 时，所有 Internet 请求都通过代理服务器发出。</span><span class="sxs-lookup"><span data-stu-id="91275-125">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="91275-126">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="91275-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="91275-127">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="91275-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="91275-128">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="91275-128">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="91275-129">指定用于分析 URI 的 HTTP 主机名比较模式。</span><span class="sxs-lookup"><span data-stu-id="91275-129">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="91275-130">此属性的类型为 `HostnameComparisonMode`，指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="91275-130">This attribute is of type `HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="91275-131">默认值为 `StrongWildcard`，表示忽略匹配项中的主机名。</span><span class="sxs-lookup"><span data-stu-id="91275-131">The default value is `StrongWildcard`, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="91275-132">一个整数值，指定为从通道接收消息的消息缓冲区管理器分配并供其使用的最大内存量。</span><span class="sxs-lookup"><span data-stu-id="91275-132">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="91275-133">默认值为 524288 (0x80000) 字节。</span><span class="sxs-lookup"><span data-stu-id="91275-133">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="91275-134">通过使用缓冲池，缓冲区管理器可将使用缓冲区的开销降到最低。</span><span class="sxs-lookup"><span data-stu-id="91275-134">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="91275-135">当消息离开通道时，服务需要使用缓冲区来处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="91275-135">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="91275-136">如果缓冲池中的内存不够用来处理消息负载，则缓冲区管理器必须从 CLR 堆分配更多内存，而这会增加垃圾回收的系统开销。</span><span class="sxs-lookup"><span data-stu-id="91275-136">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="91275-137">从 CLR 垃圾堆进行大量分配表明缓冲池太小，可以通过提高此属性指定的限制来实现更大的内存分配，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="91275-137">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="91275-138">一个整数值，指定为采用此绑定配置的终结点处理消息时存储消息的缓冲区的最大大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="91275-138">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="91275-139">默认值为 65,536 字节。</span><span class="sxs-lookup"><span data-stu-id="91275-139">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="91275-140">一个正整数，定义在采用此绑定配置的通道上可以接收的消息的最大消息大小（字节），包括消息头。</span><span class="sxs-lookup"><span data-stu-id="91275-140">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="91275-141">如果消息对于接收方而言太大，则发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="91275-141">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="91275-142">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="91275-142">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="91275-143">默认值为 65,536 字节。</span><span class="sxs-lookup"><span data-stu-id="91275-143">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="91275-144">定义用于对 SOAP 消息进行编码的编码器。</span><span class="sxs-lookup"><span data-stu-id="91275-144">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="91275-145">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="91275-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="91275-146">文本： 使用文本消息编码器。</span><span class="sxs-lookup"><span data-stu-id="91275-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="91275-147">Mtom： 使用消息传输组织机制 1.0 (MTOM) 编码器。</span><span class="sxs-lookup"><span data-stu-id="91275-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="91275-148">默认值为 Text。</span><span class="sxs-lookup"><span data-stu-id="91275-148">The default is Text.</span></span> <span data-ttu-id="91275-149">此属性的类型为 <xref:System.ServiceModel.WSMessageEncoding>。</span><span class="sxs-lookup"><span data-stu-id="91275-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="91275-150">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="91275-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="91275-151">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="91275-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="91275-152">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="91275-152">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="91275-153">此外，在同一类型的绑定中，此名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="91275-153">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="91275-154">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="91275-154">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="91275-155">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="91275-155">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="91275-156">指定绑定的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="91275-156">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="91275-157">默认值为“http://tempuri.org/Bindings”。</span><span class="sxs-lookup"><span data-stu-id="91275-157">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="91275-158">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="91275-158">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="91275-159">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="91275-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="91275-160">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="91275-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="91275-161">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="91275-161">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="91275-162">一个包含 HTTP 代理地址的 URI。</span><span class="sxs-lookup"><span data-stu-id="91275-162">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="91275-163">如果 `useSystemWebProxy` 设置为 `true`，则此设置必须为 `null`。</span><span class="sxs-lookup"><span data-stu-id="91275-163">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="91275-164">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="91275-164">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="91275-165">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="91275-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="91275-166">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="91275-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="91275-167">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="91275-167">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="91275-168">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="91275-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="91275-169">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="91275-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="91275-170">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="91275-170">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="91275-171">设置要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="91275-171">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="91275-172">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="91275-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="91275-173">-BigEndianUnicode: Unicode BigEndian 编码。</span><span class="sxs-lookup"><span data-stu-id="91275-173">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="91275-174">Unicode: 16 位编码。</span><span class="sxs-lookup"><span data-stu-id="91275-174">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="91275-175">-UTF8: 8 位编码</span><span class="sxs-lookup"><span data-stu-id="91275-175">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="91275-176">默认值为 UTF8。</span><span class="sxs-lookup"><span data-stu-id="91275-176">The default is UTF8.</span></span> <span data-ttu-id="91275-177">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="91275-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="91275-178">一个有效的 <xref:System.ServiceModel.TransferMode> 值，指定为请求或响应对消息进行缓冲处理还是流式处理。</span><span class="sxs-lookup"><span data-stu-id="91275-178">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="91275-179">一个布尔值，指定是否应在可用时使用系统的自动配置 HTTP 代理。</span><span class="sxs-lookup"><span data-stu-id="91275-179">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="91275-180">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="91275-180">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="91275-181">子元素</span><span class="sxs-lookup"><span data-stu-id="91275-181">Child Elements</span></span>  
  
|<span data-ttu-id="91275-182">元素</span><span class="sxs-lookup"><span data-stu-id="91275-182">Element</span></span>|<span data-ttu-id="91275-183">描述</span><span class="sxs-lookup"><span data-stu-id="91275-183">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91275-184">\<security></span><span class="sxs-lookup"><span data-stu-id="91275-184">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="91275-185">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="91275-185">Defines the security settings for the binding.</span></span> <span data-ttu-id="91275-186">此元素的类型为 <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="91275-186">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span></span> |  
|[<span data-ttu-id="91275-187">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="91275-187">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="91275-188">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="91275-188">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="91275-189">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="91275-189">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91275-190">父元素</span><span class="sxs-lookup"><span data-stu-id="91275-190">Parent Elements</span></span>  
  
|<span data-ttu-id="91275-191">元素</span><span class="sxs-lookup"><span data-stu-id="91275-191">Element</span></span>|<span data-ttu-id="91275-192">描述</span><span class="sxs-lookup"><span data-stu-id="91275-192">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91275-193">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="91275-193">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="91275-194">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="91275-194">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91275-195">备注</span><span class="sxs-lookup"><span data-stu-id="91275-195">Remarks</span></span>  
 <span data-ttu-id="91275-196">NetHttpsBinding 使用 HTTPS 作为传输协议来发送消息。</span><span class="sxs-lookup"><span data-stu-id="91275-196">The NetHttpsBinding uses HTTPS as the transport for sending messages.</span></span> <span data-ttu-id="91275-197">如果用于双工协定，将使用 Web Sockets。</span><span class="sxs-lookup"><span data-stu-id="91275-197">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="91275-198">如果用于请求-答复协定，则 NetHttpsBinding 的行为将类似于具有二进制编码器的 BasicHttpsBinding。</span><span class="sxs-lookup"><span data-stu-id="91275-198">When used with a request-reply contract NetHttpsBinding will behave like a BasicHttpsBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="91275-199">默认情况下，关闭安全，但可以设置的模式特性添加[\<安全 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)到以外的值的子元素`None`。</span><span class="sxs-lookup"><span data-stu-id="91275-199">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="91275-200">默认情况下，它使用“Text”消息编码和 UTF-8 文本编码。</span><span class="sxs-lookup"><span data-stu-id="91275-200">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91275-201">示例</span><span class="sxs-lookup"><span data-stu-id="91275-201">Example</span></span>  
 <span data-ttu-id="91275-202">下面的示例演示如何使用 <xref:System.ServiceModel.NetHttpBinding>，它提供 HTTPS 通信以及与第一代和第二代 Web 服务的最大互操作性。</span><span class="sxs-lookup"><span data-stu-id="91275-202">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTPS communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="91275-203">绑定是在客户端和服务的配置文件中指定的。</span><span class="sxs-lookup"><span data-stu-id="91275-203">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="91275-204">绑定类型是使用 `binding` 元素的 `<endpoint>` 属性指定的。</span><span class="sxs-lookup"><span data-stu-id="91275-204">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="91275-205">如果要配置基本绑定并更改它的某些设置，则必须定义一个绑定配置。</span><span class="sxs-lookup"><span data-stu-id="91275-205">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="91275-206">终结点必须使用 `bindingConfiguration` 元素的 `<endpoint>` 属性按名称引用绑定配置，如以下服务配置代码所示。</span><span class="sxs-lookup"><span data-stu-id="91275-206">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="netHttpsBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
    <netHttpsBinding>  
      <binding name="Binding1"   
               hostNameComparisonMode="StrongWildcard" 
               receiveTimeout="00:10:00" 
               sendTimeout="00:10:00" 
               openTimeout="00:10:00" 
               closeTimeout="00:10:00" 
               maxReceivedMessageSize="65536" 
               maxBufferSize="65536" 
               maxBufferPoolSize="524288" 
               transferMode="Buffered" 
               messageEncoding="Binary" 
               textEncoding="utf-8" 
               bypassProxyOnLocal="false" 
               useDefaultWebProxy="true">  
        <security mode="None" />  
      </binding>  
    </netHttpsBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="example"></a><span data-ttu-id="91275-207">示例</span><span class="sxs-lookup"><span data-stu-id="91275-207">Example</span></span>  
 <span data-ttu-id="91275-208">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="91275-208">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="91275-209">通过从终结点地址移除 bindingConfiguration 并从绑定移除名称，可以实现上一个示例中的功能。</span><span class="sxs-lookup"><span data-stu-id="91275-209">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name frm the binding.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="netHttpsBinding"  
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <netHttpsBinding>  
        <binding   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Binary"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </netHttpsBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="91275-210">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="91275-210">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91275-211">请参阅</span><span class="sxs-lookup"><span data-stu-id="91275-211">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="91275-212">绑定</span><span class="sxs-lookup"><span data-stu-id="91275-212">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="91275-213">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="91275-213">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="91275-214">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="91275-214">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="91275-215">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="91275-215">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
