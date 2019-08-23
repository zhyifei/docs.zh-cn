---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: 0b6f26c7b9e9d02b3ff20b53f42b09d671699ea5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919387"
---
# <a name="custombinding"></a><span data-ttu-id="a0619-101">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a0619-101">\<customBinding></span></span>

<span data-ttu-id="a0619-102">提供了对用户消息堆栈的完全控制。</span><span class="sxs-lookup"><span data-stu-id="a0619-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="a0619-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a0619-103">\<system.serviceModel></span></span>\
<span data-ttu-id="a0619-104">\<绑定 > </span><span class="sxs-lookup"><span data-stu-id="a0619-104">\<bindings></span></span>\
<span data-ttu-id="a0619-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a0619-105">\<customBinding></span></span>

## <a name="syntax"></a><span data-ttu-id="a0619-106">语法</span><span class="sxs-lookup"><span data-stu-id="a0619-106">Syntax</span></span>

```xml
<customBinding>
  <binding name="String"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
    <compositeDuplex clientBaseAddress="Uri" />
    <reliableSession acknowledgementInterval="TimeSpan"
                     advancedFlowControl="Boolean"
                     bufferedMessagesQuota="Integer"
                     inactivityTimeout="TimeSpan"
                     maxPendingChannels="Integer"
                     maxRetryCount="Integer"
                     ordered="Boolean" />
    <pnrpPeerResolver />
    <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
    <sslStreamSecurity requireClientCertificate="Boolean" />
    <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              contextMode="Cookie"
              defaultProtectionLevel="Sign"
              enableKeyDerivation="false"
              keyEntropyMode="ClientEntropy"
              messageProtectionOrder="SignBeforeEncryptAndEncryptSignature"
              securityVersion="WSSecurityXXX2005">
      <localClientSettings cacheCookies="false"
                           detectReplays="false"
                           maxCookieCachingTime="00:07:24" />
      <localServiceSettings replayCacheSize="9"
                            maxClockSkew="00:00:03"
                            replayWindow="00:07:22.2190000" />
    </security>
    <binaryMessageEncoding maxReadPoolSize="Integer"
                           maxWritePoolSize="Integer"
                           maxSessionSize="Integer" />
    <httpsTransport manualAddressing="Boolean"
                    maxMessageSize="Integer"
                    authenticationScheme="Negotiate"
                    bypassProxyOnLocal="Boolean"
                    hostNameComparisonMode="Exact"
                    mapAddressingHeadersToHttpHeaders="Boolean"
                    proxyaddress="Uri"
                    realm="String"
                    requireClientCertificate="Boolean" />
    <peerTransport manualAddressing="false"
                   maxMessageSize="20002"
                   listenIPAddress="202.10.1.9"
                   messageAuthentication="false"
                   peerNodeAuthenticationMode="None"
                   port="1000" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean">
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                            issuedCookieLifeTime="TimeSpan"
                            maxStatefulNegotiations="Integer"
                            replayCacheSize="Integer"
                            maxClockSkew="TimeSpan"
                            negotiationTimeout="TimeSpan"
                            replayWindow="TimeSpan"
                            inactivityTimeout="TimeSpan"
                            sessionKeyRenewalInterval="TimeSpan"
                            sessionKeyRolloverInterval="TimeSpan"
                            reconnectOnTransportFailure="Boolean"
                            maxConcurrentSessions="Integer"
                            timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
    </security>
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean" >
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                           issuedCookieLifeTime="TimeSpan"
                           maxStatefulNegotiations="Integer"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           negotiationTimeout="TimeSpan"
                           replayWindow="TimeSpan"
                           inactivityTimeout="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           maxConcurrentSessions="Integer"
                           timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
      <genericIssuedTokenParameters>
        <localIssuerIssuedTokenParameters keyType="SymmetricKey/PublicKey"
                                          keySize="Integer"
                                          tokenType="String" />
        <issuedTokenParametersEndpointAddress address="URI"
                                              bindingConfiguration="String"
                                              binding="String" />
        <issuedTokenClient localIssuerChannelBehaviors="String"
                           cacheIssuedTokens="Boolean"
                           maxIssuedTokenCachingTime="TimeSpan"
                           keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />
        <issuedTokenClientBehavior issuerAddress="String"
                                   behaviorConfiguration="String" />
        <issuedTokenClientBehavior address="URI"
                                   bindingConfiguration="String"
                                   binding="String" />
      </genericIssuedTokenParameters>
    </security>
  </binding>
</customBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0619-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a0619-107">Attributes and Elements</span></span>

<span data-ttu-id="a0619-108">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a0619-108">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="a0619-109">特性</span><span class="sxs-lookup"><span data-stu-id="a0619-109">Attributes</span></span>

|<span data-ttu-id="a0619-110">特性</span><span class="sxs-lookup"><span data-stu-id="a0619-110">Attribute</span></span>|<span data-ttu-id="a0619-111">描述</span><span class="sxs-lookup"><span data-stu-id="a0619-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a0619-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="a0619-112">closeTimeout</span></span>|<span data-ttu-id="a0619-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a0619-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a0619-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="a0619-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a0619-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="a0619-115">The default is 00:01:00.</span></span>|
|<span data-ttu-id="a0619-116">NAME</span><span class="sxs-lookup"><span data-stu-id="a0619-116">name</span></span>|<span data-ttu-id="a0619-117">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="a0619-117">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a0619-118">此值是用户定义的一个字符串，可充当自定义绑定的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="a0619-118">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="a0619-119">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="a0619-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a0619-120">有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="a0619-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="a0619-121">openTimeout</span><span class="sxs-lookup"><span data-stu-id="a0619-121">openTimeout</span></span>|<span data-ttu-id="a0619-122">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a0619-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a0619-123">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="a0619-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a0619-124">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="a0619-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="a0619-125">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="a0619-125">receiveTimeout</span></span>|<span data-ttu-id="a0619-126">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a0619-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a0619-127">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="a0619-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a0619-128">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="a0619-128">The default is 00:01:00.</span></span>|
|<span data-ttu-id="a0619-129">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="a0619-129">sendTimeout</span></span>|<span data-ttu-id="a0619-130">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a0619-130">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a0619-131">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="a0619-131">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a0619-132">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="a0619-132">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a0619-133">子元素</span><span class="sxs-lookup"><span data-stu-id="a0619-133">Child Elements</span></span>

|<span data-ttu-id="a0619-134">元素</span><span class="sxs-lookup"><span data-stu-id="a0619-134">Element</span></span>|<span data-ttu-id="a0619-135">描述</span><span class="sxs-lookup"><span data-stu-id="a0619-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0619-136">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="a0619-136">\<compositeDuplex></span></span>](compositeduplex.md)|<span data-ttu-id="a0619-137">对自定义绑定指定双向消息处理。</span><span class="sxs-lookup"><span data-stu-id="a0619-137">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="a0619-138">它与本身不允许进行双工通信的传输（例如，HTTP）一起使用。</span><span class="sxs-lookup"><span data-stu-id="a0619-138">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="a0619-139">与此相反，TCP 本身允许进行双工通信，并且不要求服务在将消息发送回客户端时使用此绑定元素。</span><span class="sxs-lookup"><span data-stu-id="a0619-139">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="a0619-140">客户端必须公开一个地址，以便服务进行联系和建立连接。</span><span class="sxs-lookup"><span data-stu-id="a0619-140">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="a0619-141">此客户端地址由 `ClientBaseAddress` 属性提供。</span><span class="sxs-lookup"><span data-stu-id="a0619-141">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="a0619-142">此元素的类型为 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>。</span><span class="sxs-lookup"><span data-stu-id="a0619-142">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="a0619-143">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="a0619-143">\<pnrpPeerResolver></span></span>](pnrppeerresolver.md)|<span data-ttu-id="a0619-144">指定对等名称解析协议 (PNRP) 对等名称解析程序。</span><span class="sxs-lookup"><span data-stu-id="a0619-144">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="a0619-145">此元素的类型为 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>。</span><span class="sxs-lookup"><span data-stu-id="a0619-145">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="a0619-146">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="a0619-146">\<reliableSession></span></span>](reliablesession.md)|<span data-ttu-id="a0619-147">指定 WS-ReliableMessaging 的设置。</span><span class="sxs-lookup"><span data-stu-id="a0619-147">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="a0619-148">如果将该元素添加到自定义绑定，则生成的通道可支持一次性传递保证。</span><span class="sxs-lookup"><span data-stu-id="a0619-148">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="a0619-149">此元素的类型为 <xref:System.ServiceModel.Configuration.ReliableSessionElement>。</span><span class="sxs-lookup"><span data-stu-id="a0619-149">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="a0619-150">\<security></span><span class="sxs-lookup"><span data-stu-id="a0619-150">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="a0619-151">指定自定义绑定的安全选项。</span><span class="sxs-lookup"><span data-stu-id="a0619-151">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="a0619-152">此元素的类型为 <xref:System.ServiceModel.Configuration.SecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="a0619-152">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="a0619-153">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="a0619-153">\<sslStreamSecurity></span></span>](sslstreamsecurity.md)|<span data-ttu-id="a0619-154">指定 SSL 流绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="a0619-154">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="a0619-155">此元素的类型为 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="a0619-155">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="a0619-156">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="a0619-156">\<transactionFlow></span></span>](transactionflow.md)|<span data-ttu-id="a0619-157">指定绑定支持事务流以及 `transactionProtocol` 属性将要使用的协议。</span><span class="sxs-lookup"><span data-stu-id="a0619-157">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="a0619-158">此元素的类型为 <xref:System.ServiceModel.Configuration.TransactionFlowElement>。</span><span class="sxs-lookup"><span data-stu-id="a0619-158">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="a0619-159">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="a0619-159">\<windowsStreamSecurity></span></span>](windowsstreamsecurity.md)|<span data-ttu-id="a0619-160">指定自定义绑定的流安全选项。</span><span class="sxs-lookup"><span data-stu-id="a0619-160">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="a0619-161">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="a0619-161">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a0619-162">父元素</span><span class="sxs-lookup"><span data-stu-id="a0619-162">Parent Elements</span></span>

|<span data-ttu-id="a0619-163">元素</span><span class="sxs-lookup"><span data-stu-id="a0619-163">Element</span></span>|<span data-ttu-id="a0619-164">描述</span><span class="sxs-lookup"><span data-stu-id="a0619-164">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="a0619-165">绑定</span><span class="sxs-lookup"><span data-stu-id="a0619-165">bindings</span></span>|<span data-ttu-id="a0619-166">包含 Windows Communication Foundation 应用程序的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="a0619-166">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a0619-167">备注</span><span class="sxs-lookup"><span data-stu-id="a0619-167">Remarks</span></span>

<span data-ttu-id="a0619-168">自定义绑定提供了对 WCF 消息堆栈的完全控制。</span><span class="sxs-lookup"><span data-stu-id="a0619-168">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="a0619-169">通过添加特定实体的配置元素，可以创建特别定制的绑定。</span><span class="sxs-lookup"><span data-stu-id="a0619-169">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="a0619-170">例如，用户可以合并 `httpsTransport` 节、`reliableSession` 节和 `security` 节以创建一个安全可靠的基于 https 的绑定。</span><span class="sxs-lookup"><span data-stu-id="a0619-170">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="a0619-171">单个绑定按照堆栈元素在堆栈上出现的顺序来指定它们的配置元素，从而定义消息堆栈。</span><span class="sxs-lookup"><span data-stu-id="a0619-171">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="a0619-172">每个元素都定义和配置了该堆栈的一个元素。</span><span class="sxs-lookup"><span data-stu-id="a0619-172">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="a0619-173">在每个自定义绑定中，必须有且只能有一个传输元素。</span><span class="sxs-lookup"><span data-stu-id="a0619-173">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="a0619-174">如果没有该元素，消息堆栈将是不完整的。</span><span class="sxs-lookup"><span data-stu-id="a0619-174">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="a0619-175">元素在堆栈中出现的顺序非常重要，因为在将操作应用于消息时会采用该顺序。</span><span class="sxs-lookup"><span data-stu-id="a0619-175">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="a0619-176">建议的堆栈元素顺序如下：</span><span class="sxs-lookup"><span data-stu-id="a0619-176">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="a0619-177">事务（可选）</span><span class="sxs-lookup"><span data-stu-id="a0619-177">Transactions (optional)</span></span>

2. <span data-ttu-id="a0619-178">可靠消息（可选）</span><span class="sxs-lookup"><span data-stu-id="a0619-178">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="a0619-179">安全（可选）</span><span class="sxs-lookup"><span data-stu-id="a0619-179">Security (optional)</span></span>

4. <span data-ttu-id="a0619-180">传输</span><span class="sxs-lookup"><span data-stu-id="a0619-180">Transport</span></span>

5. <span data-ttu-id="a0619-181">编码器（可选）</span><span class="sxs-lookup"><span data-stu-id="a0619-181">Encoder (optional)</span></span>

<span data-ttu-id="a0619-182">当系统提供的某个绑定不符合服务需求时，应使用自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="a0619-182">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="a0619-183">例如，自定义绑定可用于实现在服务终结点使用新的传输或新的编码器。</span><span class="sxs-lookup"><span data-stu-id="a0619-183">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="a0619-184">自定义绑定是使用以特定顺序“堆叠”的绑定元素集合中的某个 <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> 构造的，顺序如下：</span><span class="sxs-lookup"><span data-stu-id="a0619-184">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="a0619-185">最顶层是一个允许流事务的可选 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="a0619-185">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="a0619-186">接下来是一个可选的 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>，它提供了 WS-ReliableMessaging 规范中定义的会话和排序机制。</span><span class="sxs-lookup"><span data-stu-id="a0619-186">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="a0619-187">此会话概念可跨 SOAP 和传输中介。</span><span class="sxs-lookup"><span data-stu-id="a0619-187">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="a0619-188">接下来是一个可选的安全绑定元素，它提供了授权、身份验证、保护和机密性之类的安全功能。</span><span class="sxs-lookup"><span data-stu-id="a0619-188">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="a0619-189">Windows Communication Foundation (WCF) 提供以下安全绑定元素:</span><span class="sxs-lookup"><span data-stu-id="a0619-189">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="a0619-190">接着是由下面的绑定元素指定的多个可选消息模式：</span><span class="sxs-lookup"><span data-stu-id="a0619-190">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="a0619-191">再下面是以下可选的传输升级/帮助器绑定元素：</span><span class="sxs-lookup"><span data-stu-id="a0619-191">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="a0619-192">再接下来是一个必需的消息编码绑定元素。</span><span class="sxs-lookup"><span data-stu-id="a0619-192">Next is a required message encoding binding element.</span></span> <span data-ttu-id="a0619-193">可以使用自己的传输或者使用以下消息编码绑定之一：</span><span class="sxs-lookup"><span data-stu-id="a0619-193">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="a0619-194">底层是一个必需的传输元素。</span><span class="sxs-lookup"><span data-stu-id="a0619-194">At the bottom is a required transport element.</span></span> <span data-ttu-id="a0619-195">你可以使用自己的传输, 或者使用 Windows Communication Foundation (WCF) 提供的传输绑定元素之一:</span><span class="sxs-lookup"><span data-stu-id="a0619-195">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="a0619-196">下表总结了每层的选项。</span><span class="sxs-lookup"><span data-stu-id="a0619-196">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="a0619-197">层</span><span class="sxs-lookup"><span data-stu-id="a0619-197">Layer</span></span>|<span data-ttu-id="a0619-198">选项</span><span class="sxs-lookup"><span data-stu-id="a0619-198">Options</span></span>|<span data-ttu-id="a0619-199">必需</span><span class="sxs-lookup"><span data-stu-id="a0619-199">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="a0619-200">事务流</span><span class="sxs-lookup"><span data-stu-id="a0619-200">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="a0619-201">No</span><span class="sxs-lookup"><span data-stu-id="a0619-201">No</span></span>|
|<span data-ttu-id="a0619-202">可靠性</span><span class="sxs-lookup"><span data-stu-id="a0619-202">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="a0619-203">No</span><span class="sxs-lookup"><span data-stu-id="a0619-203">No</span></span>|
|<span data-ttu-id="a0619-204">安全性</span><span class="sxs-lookup"><span data-stu-id="a0619-204">Security</span></span>|<span data-ttu-id="a0619-205">对称、非对称、传输级</span><span class="sxs-lookup"><span data-stu-id="a0619-205">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="a0619-206">No</span><span class="sxs-lookup"><span data-stu-id="a0619-206">No</span></span>|
|<span data-ttu-id="a0619-207">形状更改</span><span class="sxs-lookup"><span data-stu-id="a0619-207">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="a0619-208">No</span><span class="sxs-lookup"><span data-stu-id="a0619-208">No</span></span>|
|<span data-ttu-id="a0619-209">传输升级</span><span class="sxs-lookup"><span data-stu-id="a0619-209">Transport Upgrades</span></span>|<span data-ttu-id="a0619-210">SSL 流、Windows 流、对等解析程序</span><span class="sxs-lookup"><span data-stu-id="a0619-210">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="a0619-211">No</span><span class="sxs-lookup"><span data-stu-id="a0619-211">No</span></span>|
|<span data-ttu-id="a0619-212">编码</span><span class="sxs-lookup"><span data-stu-id="a0619-212">Encoding</span></span>|<span data-ttu-id="a0619-213">文本、二进制、MTOM、自定义</span><span class="sxs-lookup"><span data-stu-id="a0619-213">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="a0619-214">是</span><span class="sxs-lookup"><span data-stu-id="a0619-214">Yes</span></span>|
|<span data-ttu-id="a0619-215">传输</span><span class="sxs-lookup"><span data-stu-id="a0619-215">Transport</span></span>|<span data-ttu-id="a0619-216">TCP、命名管道、HTTP、HTTPS、MSMQ 风格、自定义</span><span class="sxs-lookup"><span data-stu-id="a0619-216">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="a0619-217">是</span><span class="sxs-lookup"><span data-stu-id="a0619-217">Yes</span></span>|

<span data-ttu-id="a0619-218">此外，可以定义自己的绑定元素，并将它们插在前面定义的任何层之间。</span><span class="sxs-lookup"><span data-stu-id="a0619-218">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="a0619-219">有关如何使用自定义绑定来修改系统提供的绑定的讨论, 请参阅[如何:自定义系统提供的绑定](../../../wcf/extending/how-to-customize-a-system-provided-binding.md)。</span><span class="sxs-lookup"><span data-stu-id="a0619-219">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0619-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0619-220">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a0619-221">\<binding></span><span class="sxs-lookup"><span data-stu-id="a0619-221">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="a0619-222">绑定</span><span class="sxs-lookup"><span data-stu-id="a0619-222">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a0619-223">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="a0619-223">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a0619-224">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="a0619-224">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a0619-225">customBinding 元素</span><span class="sxs-lookup"><span data-stu-id="a0619-225">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="a0619-226">绑定</span><span class="sxs-lookup"><span data-stu-id="a0619-226">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a0619-227">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="a0619-227">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a0619-228">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a0619-228">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
