---
title: '&lt;wsHttpBinding&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: 1cc79be0b9a35aacf0c85a0944be9ee710139925
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762255"
---
# <a name="ltwshttpbindinggt"></a><span data-ttu-id="53141-102">&lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="53141-102">&lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="53141-103">定义一个适合于非双工服务约定的安全、可靠且可互操作的绑定。</span><span class="sxs-lookup"><span data-stu-id="53141-103">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="53141-104">该绑定为保证可靠性实现 WS-ReliableMessaging 规范，为保证消息安全性和进行身份验证实现 WS-Security 规范。</span><span class="sxs-lookup"><span data-stu-id="53141-104">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="53141-105">传输协议是 HTTP，消息编码方式是 Text/XML 编码。</span><span class="sxs-lookup"><span data-stu-id="53141-105">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
 <span data-ttu-id="53141-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="53141-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="53141-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="53141-107">\<bindings></span></span>  
<span data-ttu-id="53141-108">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="53141-108">\<wsHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53141-109">语法</span><span class="sxs-lookup"><span data-stu-id="53141-109">Syntax</span></span>  
  
```xml  
<wsHttpBinding>  
    <binding   
        allowCookies="Boolean"  
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"  
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="Integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
                textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
        <security mode="Message/None/Transport/TransportWithCredential">  
           <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
                proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                realm="string" />  
          <message   
             algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                          clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
             establishSecurityContext="Boolean"  
             negotiateServiceCredential="Boolean" />  
        </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53141-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="53141-110">Attributes and Elements</span></span>  
 <span data-ttu-id="53141-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="53141-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53141-112">特性</span><span class="sxs-lookup"><span data-stu-id="53141-112">Attributes</span></span>  
  
|<span data-ttu-id="53141-113">特性</span><span class="sxs-lookup"><span data-stu-id="53141-113">Attribute</span></span>|<span data-ttu-id="53141-114">描述</span><span class="sxs-lookup"><span data-stu-id="53141-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53141-115">allowCookies</span><span class="sxs-lookup"><span data-stu-id="53141-115">allowCookies</span></span>|<span data-ttu-id="53141-116">一个布尔值，指示客户端是否接受 Cookie 并在今后的请求中传播这些 Cookie。</span><span class="sxs-lookup"><span data-stu-id="53141-116">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="53141-117">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="53141-117">The default is false.</span></span><br /><br /> <span data-ttu-id="53141-118">在与使用 Cookie 的 ASMX Web 服务进行交互时，可以使用此属性。</span><span class="sxs-lookup"><span data-stu-id="53141-118">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="53141-119">通过这种方式，可以确保从服务器返回的 Cookie 自动复制到客户端今后对该服务的所有请求。</span><span class="sxs-lookup"><span data-stu-id="53141-119">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="53141-120">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="53141-120">bypassProxyOnLocal</span></span>|<span data-ttu-id="53141-121">一个布尔值，指示是否对本地地址不使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="53141-121">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="53141-122">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="53141-122">The default is `false`.</span></span>|  
|<span data-ttu-id="53141-123">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="53141-123">closeTimeout</span></span>|<span data-ttu-id="53141-124">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="53141-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="53141-125">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="53141-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="53141-126">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="53141-126">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="53141-127">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="53141-127">hostnameComparisonMode</span></span>|<span data-ttu-id="53141-128">指定用于分析 URI 的 HTTP 主机名比较模式。</span><span class="sxs-lookup"><span data-stu-id="53141-128">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="53141-129">此属性的类型为 <xref:System.ServiceModel.HostNameComparisonMode>，指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="53141-129">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="53141-130">默认值为 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>，表示忽略匹配项中的主机名。</span><span class="sxs-lookup"><span data-stu-id="53141-130">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="53141-131">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="53141-131">maxBufferPoolSize</span></span>|<span data-ttu-id="53141-132">一个整数，指定此绑定的最大缓冲池大小。</span><span class="sxs-lookup"><span data-stu-id="53141-132">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="53141-133">默认值为 524,288 字节 (512 \* 1024)。</span><span class="sxs-lookup"><span data-stu-id="53141-133">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="53141-134">Windows Communication Foundation (WCF) 的许多部件使用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="53141-134">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="53141-135">每次使用缓冲区时，创建和销毁它们都将占用大量资源，而缓冲区的垃圾回收过程也是如此。</span><span class="sxs-lookup"><span data-stu-id="53141-135">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="53141-136">利用缓冲池，可以从缓冲池中获得缓冲区，使用缓冲区，然后在完成工作后将其返回给缓冲池。</span><span class="sxs-lookup"><span data-stu-id="53141-136">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="53141-137">这样就避免了创建和销毁缓冲区的系统开销。</span><span class="sxs-lookup"><span data-stu-id="53141-137">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="53141-138">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="53141-138">maxReceivedMessageSize</span></span>|<span data-ttu-id="53141-139">一个正整数，指定采用此绑定配置的通道上可以接收的最大消息大小（字节），包括消息头。</span><span class="sxs-lookup"><span data-stu-id="53141-139">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="53141-140">如果消息超出此限制，则发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="53141-140">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="53141-141">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="53141-141">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="53141-142">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="53141-142">The default is 65536.</span></span>|  
|<span data-ttu-id="53141-143">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="53141-143">messageEncoding</span></span>|<span data-ttu-id="53141-144">定义用于对消息进行编码的编码器。</span><span class="sxs-lookup"><span data-stu-id="53141-144">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="53141-145">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="53141-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="53141-146">文本： 使用文本消息编码器。</span><span class="sxs-lookup"><span data-stu-id="53141-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="53141-147">Mtom： 使用消息传输组织机制 1.0 (MTOM) 编码器。</span><span class="sxs-lookup"><span data-stu-id="53141-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="53141-148">-默认值为 Text。</span><span class="sxs-lookup"><span data-stu-id="53141-148">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="53141-149">此属性的类型为 <xref:System.ServiceModel.WSMessageEncoding>。</span><span class="sxs-lookup"><span data-stu-id="53141-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="53141-150">name</span><span class="sxs-lookup"><span data-stu-id="53141-150">name</span></span>|<span data-ttu-id="53141-151">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="53141-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="53141-152">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="53141-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="53141-153">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="53141-153">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="53141-154">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="53141-154">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="53141-155">openTimeout</span><span class="sxs-lookup"><span data-stu-id="53141-155">openTimeout</span></span>|<span data-ttu-id="53141-156">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="53141-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="53141-157">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="53141-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="53141-158">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="53141-158">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="53141-159">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="53141-159">proxyAddress</span></span>|<span data-ttu-id="53141-160">一个指定 HTTP 代理的地址的 URI。</span><span class="sxs-lookup"><span data-stu-id="53141-160">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="53141-161">如果 `useSystemWebProxy` 为 `true`，则此设置必须为 `null`。</span><span class="sxs-lookup"><span data-stu-id="53141-161">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="53141-162">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="53141-162">The default is `null`.</span></span>|  
|<span data-ttu-id="53141-163">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="53141-163">receiveTimeout</span></span>|<span data-ttu-id="53141-164">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="53141-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="53141-165">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="53141-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="53141-166">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="53141-166">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="53141-167">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="53141-167">sendTimeout</span></span>|<span data-ttu-id="53141-168">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="53141-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="53141-169">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="53141-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="53141-170">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="53141-170">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="53141-171">textEncoding</span><span class="sxs-lookup"><span data-stu-id="53141-171">textEncoding</span></span>|<span data-ttu-id="53141-172">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="53141-172">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="53141-173">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="53141-173">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="53141-174">-UnicodeFffeTextEncoding: Unicode BigEndian 编码。</span><span class="sxs-lookup"><span data-stu-id="53141-174">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="53141-175">-Utf16TextEncoding: 16 位编码。</span><span class="sxs-lookup"><span data-stu-id="53141-175">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="53141-176">-Utf8TextEncoding: 8 位编码。</span><span class="sxs-lookup"><span data-stu-id="53141-176">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="53141-177">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="53141-177">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="53141-178">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="53141-178">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="53141-179">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="53141-179">transactionFlow</span></span>|<span data-ttu-id="53141-180">一个布尔值，指定绑定是否支持流动 WS-Transactions。</span><span class="sxs-lookup"><span data-stu-id="53141-180">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="53141-181">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="53141-181">The default is `false`.</span></span>|  
|<span data-ttu-id="53141-182">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="53141-182">useDefaultWebProxy</span></span>|<span data-ttu-id="53141-183">一个布尔值，指定是否使用系统的自动配置 HTTP 代理。</span><span class="sxs-lookup"><span data-stu-id="53141-183">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="53141-184">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="53141-184">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53141-185">子元素</span><span class="sxs-lookup"><span data-stu-id="53141-185">Child Elements</span></span>  
  
|<span data-ttu-id="53141-186">元素</span><span class="sxs-lookup"><span data-stu-id="53141-186">Element</span></span>|<span data-ttu-id="53141-187">描述</span><span class="sxs-lookup"><span data-stu-id="53141-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53141-188">\<security></span><span class="sxs-lookup"><span data-stu-id="53141-188">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="53141-189">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="53141-189">Defines the security settings for the binding.</span></span> <span data-ttu-id="53141-190">此元素的类型为 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="53141-190">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="53141-191">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="53141-191">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="53141-192">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="53141-192">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="53141-193">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="53141-193">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="53141-194">reliableSession</span><span class="sxs-lookup"><span data-stu-id="53141-194">reliableSession</span></span>](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="53141-195">指定是否在通道终结点之间建立可靠会话。</span><span class="sxs-lookup"><span data-stu-id="53141-195">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53141-196">父元素</span><span class="sxs-lookup"><span data-stu-id="53141-196">Parent Elements</span></span>  
  
|<span data-ttu-id="53141-197">元素</span><span class="sxs-lookup"><span data-stu-id="53141-197">Element</span></span>|<span data-ttu-id="53141-198">描述</span><span class="sxs-lookup"><span data-stu-id="53141-198">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53141-199">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="53141-199">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="53141-200">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="53141-200">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53141-201">备注</span><span class="sxs-lookup"><span data-stu-id="53141-201">Remarks</span></span>  
 <span data-ttu-id="53141-202">`WSHttpBinding` 与 `BasicHttpBinding` 相似，但是会提供更多的 Web 服务功能。</span><span class="sxs-lookup"><span data-stu-id="53141-202">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="53141-203">与 BasicHttpBinding 一样，它也使用 HTTP 传输并提供消息安全，但它还提供事务、可靠消息传递和 WS-Addressing，这些功能要么在默认情况下已启用，要么通过单一控制设置来提供。</span><span class="sxs-lookup"><span data-stu-id="53141-203">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53141-204">示例</span><span class="sxs-lookup"><span data-stu-id="53141-204">Example</span></span>  
  
```xml  
<configuration>  
    <system.ServiceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding   
                    closeTimeout="00:00:10"  
                    openTimeout="00:00:20"   
                    receiveTimeout="00:00:30"  
                    sendTimeout="00:00:40"  
                    bypassProxyOnLocal="false"  
                    transactionFlow="false"   
                    hostNameComparisonMode="WeakWildcard"  
                    maxReceivedMessageSize="1000"  
                    messageEncoding="Mtom"   
                    proxyAddress="http://foo/bar"  
                    textEncoding="utf-16"  
                    useDefaultWebProxy="false">  
                    <reliableSession ordered="false"  
                         inactivityTimeout="00:02:00"  
                         enabled="true" />  
                    <security mode="Transport">  
                         <transport clientCredentialType="Digest"  
                            proxyCredentialType="None"  
                            realm="someRealm" />  
                         <message clientCredentialType="Windows"  
                            negotiateServiceCredential="false"  
                            algorithmSuite="Aes128"   
                            defaultProtectionLevel="None" />  
                    </security>  
                </binding>  
           </wsHttpBinding>  
        </bindings>  
    </system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53141-205">请参阅</span><span class="sxs-lookup"><span data-stu-id="53141-205">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpBinding>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement>  
 [<span data-ttu-id="53141-206">绑定</span><span class="sxs-lookup"><span data-stu-id="53141-206">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="53141-207">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="53141-207">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="53141-208">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="53141-208">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="53141-209">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="53141-209">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
