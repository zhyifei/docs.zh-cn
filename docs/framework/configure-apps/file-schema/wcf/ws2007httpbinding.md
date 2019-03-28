---
title: <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
ms.openlocfilehash: 01b8f20607de1cdd9c6b1ad9fc030c1d050ed749
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410636"
---
# <a name="ws2007httpbinding"></a><span data-ttu-id="90724-101">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="90724-101">\<ws2007HttpBinding></span></span>
<span data-ttu-id="90724-102">定义一个可互操作的绑定，该绑定为正确版本的 <xref:System.ServiceModel.WSHttpBinding.Security%2A>、<xref:System.ServiceModel.ReliableSession> 和 <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> 绑定元素提供支持。</span><span class="sxs-lookup"><span data-stu-id="90724-102">Defines an interoperable binding that provides support for the correct versions of the <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, and <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> binding elements.</span></span>  
  
 <span data-ttu-id="90724-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="90724-103">\<system.serviceModel></span></span>  
<span data-ttu-id="90724-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="90724-104">\<bindings></span></span>  
<span data-ttu-id="90724-105">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="90724-105">\<ws2007HttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90724-106">语法</span><span class="sxs-lookup"><span data-stu-id="90724-106">Syntax</span></span>  
  
```xml  
<ws2007HttpBinding>
  <binding allowCookies="Boolean"
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
        <message clientCredentialType ="Certificate/IssuedToken/None/UserName/Windows"
                 negotiateServiceCredential="Boolean"
                 algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
                 establishSecurityContext="Boolean"
                 negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90724-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="90724-107">Attributes and Elements</span></span>  
 <span data-ttu-id="90724-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="90724-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90724-109">特性</span><span class="sxs-lookup"><span data-stu-id="90724-109">Attributes</span></span>  
  
|<span data-ttu-id="90724-110">特性</span><span class="sxs-lookup"><span data-stu-id="90724-110">Attribute</span></span>|<span data-ttu-id="90724-111">描述</span><span class="sxs-lookup"><span data-stu-id="90724-111">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="90724-112">一个值，指示客户端是否接受 cookie 并根据将来的请求对其进行传播。</span><span class="sxs-lookup"><span data-stu-id="90724-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="90724-113">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="90724-113">The default is `false`.</span></span><br /><br /> <span data-ttu-id="90724-114">在与使用 Cookie 的 ASP.NET Web 服务 (ASMX) 进行交互时，可以使用此属性。</span><span class="sxs-lookup"><span data-stu-id="90724-114">You can use this property when you interact with ASP.NET Web services (ASMX) that use cookies.</span></span> <span data-ttu-id="90724-115">这确保了服务器返回的 Cookie 会自动复制到客户端今后对该服务的所有请求。</span><span class="sxs-lookup"><span data-stu-id="90724-115">This ensures that cookies that the server returns are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="90724-116">一个值，指示是否对本地地址不使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="90724-116">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="90724-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="90724-117">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="90724-118">一个 <xref:System.TimeSpan> 值，指定完成关闭操作的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="90724-118">A <xref:System.TimeSpan> value that specifies the time interval for a close operation to complete.</span></span> <span data-ttu-id="90724-119">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="90724-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="90724-120">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="90724-120">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="90724-121">指定用于分析统一资源标识符 (URI) 的 HTTP 主机名比较模式。</span><span class="sxs-lookup"><span data-stu-id="90724-121">Specifies the HTTP hostname comparison mode used to parse Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="90724-122">此属性的类型为 <xref:System.ServiceModel.HostNameComparisonMode>，指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="90724-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="90724-123">默认值为 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>，表示忽略匹配项中的主机名。</span><span class="sxs-lookup"><span data-stu-id="90724-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="90724-124">此绑定的最大缓冲池大小。</span><span class="sxs-lookup"><span data-stu-id="90724-124">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="90724-125">默认值为 524,288 字节 (512 × 1,024)。</span><span class="sxs-lookup"><span data-stu-id="90724-125">The default is 524,288 bytes (512 × 1,024).</span></span> <span data-ttu-id="90724-126">Windows Communication Foundation (WCF) 的许多部件使用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="90724-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="90724-127">每次使用缓冲区时，创建和销毁它们会占用大量资源，而缓冲区的垃圾回收过程也是如此。</span><span class="sxs-lookup"><span data-stu-id="90724-127">Creating and destroying buffers each time they are used is expensive, as is garbage collection for buffers.</span></span> <span data-ttu-id="90724-128">利用缓冲池，可以从缓冲池中获得缓冲区，使用缓冲区，然后在完成工作后将其返回到缓冲池。</span><span class="sxs-lookup"><span data-stu-id="90724-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool when you are done.</span></span> <span data-ttu-id="90724-129">这样就避免了创建和销毁缓冲区的系统开销。</span><span class="sxs-lookup"><span data-stu-id="90724-129">This avoids the overhead in creating and destroying buffers.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="90724-130">使用此绑定配置的通道可以接收的最大消息大小（包括标头），单位为字节。</span><span class="sxs-lookup"><span data-stu-id="90724-130">The maximum message size, in bytes, including headers, which a channel configured with this binding, can receive.</span></span> <span data-ttu-id="90724-131">如果消息超出此限制，则发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="90724-131">The sender of a message exceeding this limit receives a SOAP fault.</span></span> <span data-ttu-id="90724-132">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="90724-132">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="90724-133">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="90724-133">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="90724-134">定义用于对消息进行编码的编码器。</span><span class="sxs-lookup"><span data-stu-id="90724-134">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="90724-135">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="90724-135">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="90724-136">-   `Text`：使用文本消息编码器。</span><span class="sxs-lookup"><span data-stu-id="90724-136">-   `Text`: Use a text message encoder.</span></span><br /><span data-ttu-id="90724-137">-   `Mtom`：使用消息传输组织机制 1.0 (MTOM) 编码器。</span><span class="sxs-lookup"><span data-stu-id="90724-137">-   `Mtom`: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="90724-138">默认值为 `Text`。</span><span class="sxs-lookup"><span data-stu-id="90724-138">The default is `Text`.</span></span><br /><br /> <span data-ttu-id="90724-139">此属性的类型为 <xref:System.ServiceModel.WSMessageEncoding>。</span><span class="sxs-lookup"><span data-stu-id="90724-139">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="90724-140">绑定的配置名称。</span><span class="sxs-lookup"><span data-stu-id="90724-140">The configuration name of the binding.</span></span> <span data-ttu-id="90724-141">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="90724-141">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="90724-142">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="90724-142">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="90724-143">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="90724-143">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="90724-144">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="90724-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="90724-145">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="90724-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="90724-146">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="90724-146">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="90724-147">一个指定 HTTP 代理的地址的 URI。</span><span class="sxs-lookup"><span data-stu-id="90724-147">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="90724-148">如果 `useSystemWebProxy` 为 `true`，则此设置必须为 `null`。</span><span class="sxs-lookup"><span data-stu-id="90724-148">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="90724-149">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="90724-149">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="90724-150">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="90724-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="90724-151">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="90724-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="90724-152">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="90724-152">The default is 00:01:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="90724-153">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="90724-153">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="90724-154">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="90724-154">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="90724-155">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="90724-155">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="90724-156">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="90724-156">Specifies the character set encoding to use for emitting messages on the binding.</span></span> <span data-ttu-id="90724-157">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="90724-157">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="90724-158">-   `UnicodeFffeTextEncoding`：Unicode Big Endian 编码。</span><span class="sxs-lookup"><span data-stu-id="90724-158">-   `UnicodeFffeTextEncoding`: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="90724-159">-   `Utf16TextEncoding`：16 位编码。</span><span class="sxs-lookup"><span data-stu-id="90724-159">-   `Utf16TextEncoding`: 16-bit encoding.</span></span><br /><span data-ttu-id="90724-160">-   `Utf8TextEncoding`：8 位编码。</span><span class="sxs-lookup"><span data-stu-id="90724-160">-   `Utf8TextEncoding`: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="90724-161">默认值为 `Utf8TextEncoding`。</span><span class="sxs-lookup"><span data-stu-id="90724-161">The default is `Utf8TextEncoding`.</span></span><br /><br /> <span data-ttu-id="90724-162">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="90724-162">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="90724-163">一个值，指定绑定是否支持流动 WS-Transactions。</span><span class="sxs-lookup"><span data-stu-id="90724-163">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="90724-164">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="90724-164">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="90724-165">一个值，指定是否使用系统的自动配置 HTTP 代理。</span><span class="sxs-lookup"><span data-stu-id="90724-165">A value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="90724-166">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="90724-166">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90724-167">子元素</span><span class="sxs-lookup"><span data-stu-id="90724-167">Child Elements</span></span>  
  
|<span data-ttu-id="90724-168">元素</span><span class="sxs-lookup"><span data-stu-id="90724-168">Element</span></span>|<span data-ttu-id="90724-169">描述</span><span class="sxs-lookup"><span data-stu-id="90724-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90724-170">\<security></span><span class="sxs-lookup"><span data-stu-id="90724-170">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="90724-171">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="90724-171">Defines the security settings for the binding.</span></span> <span data-ttu-id="90724-172">此元素的类型为 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="90724-172">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="90724-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="90724-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="90724-174">定义用此绑定配置的终结点可处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="90724-174">Defines the constraints on the complexity of SOAP messages that endpoints configured with this binding can process.</span></span> <span data-ttu-id="90724-175">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="90724-175">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="90724-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="90724-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="90724-177">指定是否在通道终结点之间建立可靠会话。</span><span class="sxs-lookup"><span data-stu-id="90724-177">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90724-178">父元素</span><span class="sxs-lookup"><span data-stu-id="90724-178">Parent Elements</span></span>  
  
|<span data-ttu-id="90724-179">元素</span><span class="sxs-lookup"><span data-stu-id="90724-179">Element</span></span>|<span data-ttu-id="90724-180">描述</span><span class="sxs-lookup"><span data-stu-id="90724-180">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90724-181">\<bindings></span><span class="sxs-lookup"><span data-stu-id="90724-181">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="90724-182">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="90724-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90724-183">备注</span><span class="sxs-lookup"><span data-stu-id="90724-183">Remarks</span></span>  
 <span data-ttu-id="90724-184">`WS2007HttpBinding` 会添加与 `WSHttpBinding` 类似的系统提供的绑定，但使用 ReliableSession、Security 和 TransactionFlow 协议的结构化信息标准促进组织 (OASIS) 标准版本。</span><span class="sxs-lookup"><span data-stu-id="90724-184">The `WS2007HttpBinding` adds a system-provided binding similar to `WSHttpBinding` but uses the Organization for the Advancement of Structured Information Standards (OASIS) standard versions of the ReliableSession, Security, and TransactionFlow protocols.</span></span> <span data-ttu-id="90724-185">使用此绑定时，无需对对象模型或默认设置进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="90724-185">No changes to the object model or default settings are required when using this binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90724-186">示例</span><span class="sxs-lookup"><span data-stu-id="90724-186">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007HttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
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
      </ws2007HttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="90724-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="90724-187">See also</span></span>
- <xref:System.ServiceModel.WS2007HttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>
- [<span data-ttu-id="90724-188">绑定</span><span class="sxs-lookup"><span data-stu-id="90724-188">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="90724-189">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="90724-189">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="90724-190">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="90724-190">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="90724-191">\<binding></span><span class="sxs-lookup"><span data-stu-id="90724-191">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
