---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: 1fd0a12b62c416ce71946e59e7868abc7638a274
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398125"
---
# <a name="custombinding"></a><span data-ttu-id="f2e4a-101">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f2e4a-101">\<customBinding></span></span>

<span data-ttu-id="f2e4a-102">提供了对用户消息堆栈的完全控制。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="f2e4a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2e4a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f2e4a-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f2e4a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f2e4a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="f2e4a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="f2e4a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customBinding >**</span><span class="sxs-lookup"><span data-stu-id="f2e4a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f2e4a-107">语法</span><span class="sxs-lookup"><span data-stu-id="f2e4a-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="f2e4a-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f2e4a-108">Attributes and Elements</span></span>

<span data-ttu-id="f2e4a-109">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-109">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="f2e4a-110">特性</span><span class="sxs-lookup"><span data-stu-id="f2e4a-110">Attributes</span></span>

|<span data-ttu-id="f2e4a-111">特性</span><span class="sxs-lookup"><span data-stu-id="f2e4a-111">Attribute</span></span>|<span data-ttu-id="f2e4a-112">描述</span><span class="sxs-lookup"><span data-stu-id="f2e4a-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="f2e4a-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="f2e4a-113">closeTimeout</span></span>|<span data-ttu-id="f2e4a-114">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f2e4a-115">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f2e4a-116">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-116">The default is 00:01:00.</span></span>|
|<span data-ttu-id="f2e4a-117">NAME</span><span class="sxs-lookup"><span data-stu-id="f2e4a-117">name</span></span>|<span data-ttu-id="f2e4a-118">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-118">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f2e4a-119">此值是用户定义的一个字符串，可充当自定义绑定的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-119">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="f2e4a-120">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f2e4a-121">有关默认配置和无值绑定和行为的详细信息，请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="f2e4a-122">openTimeout</span><span class="sxs-lookup"><span data-stu-id="f2e4a-122">openTimeout</span></span>|<span data-ttu-id="f2e4a-123">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f2e4a-124">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f2e4a-125">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-125">The default is 00:01:00.</span></span>|
|<span data-ttu-id="f2e4a-126">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="f2e4a-126">receiveTimeout</span></span>|<span data-ttu-id="f2e4a-127">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f2e4a-128">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f2e4a-129">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-129">The default is 00:01:00.</span></span>|
|<span data-ttu-id="f2e4a-130">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="f2e4a-130">sendTimeout</span></span>|<span data-ttu-id="f2e4a-131">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-131">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f2e4a-132">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-132">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f2e4a-133">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-133">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f2e4a-134">子元素</span><span class="sxs-lookup"><span data-stu-id="f2e4a-134">Child Elements</span></span>

|<span data-ttu-id="f2e4a-135">元素</span><span class="sxs-lookup"><span data-stu-id="f2e4a-135">Element</span></span>|<span data-ttu-id="f2e4a-136">描述</span><span class="sxs-lookup"><span data-stu-id="f2e4a-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f2e4a-137">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="f2e4a-137">\<compositeDuplex></span></span>](compositeduplex.md)|<span data-ttu-id="f2e4a-138">对自定义绑定指定双向消息处理。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-138">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="f2e4a-139">它与本身不允许进行双工通信的传输（例如，HTTP）一起使用。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-139">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="f2e4a-140">与此相反，TCP 本身允许进行双工通信，并且不要求服务在将消息发送回客户端时使用此绑定元素。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-140">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="f2e4a-141">客户端必须公开一个地址，以便服务进行联系和建立连接。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-141">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="f2e4a-142">此客户端地址由 `ClientBaseAddress` 属性提供。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-142">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="f2e4a-143">此元素的类型为 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-143">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="f2e4a-144">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="f2e4a-144">\<pnrpPeerResolver></span></span>](pnrppeerresolver.md)|<span data-ttu-id="f2e4a-145">指定对等名称解析协议 (PNRP) 对等名称解析程序。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-145">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="f2e4a-146">此元素的类型为 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-146">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="f2e4a-147">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="f2e4a-147">\<reliableSession></span></span>](reliablesession.md)|<span data-ttu-id="f2e4a-148">指定 WS-ReliableMessaging 的设置。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-148">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="f2e4a-149">如果将该元素添加到自定义绑定，则生成的通道可支持一次性传递保证。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-149">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="f2e4a-150">此元素的类型为 <xref:System.ServiceModel.Configuration.ReliableSessionElement>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-150">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="f2e4a-151">\<security></span><span class="sxs-lookup"><span data-stu-id="f2e4a-151">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="f2e4a-152">指定自定义绑定的安全选项。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-152">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="f2e4a-153">此元素的类型为 <xref:System.ServiceModel.Configuration.SecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-153">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="f2e4a-154">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="f2e4a-154">\<sslStreamSecurity></span></span>](sslstreamsecurity.md)|<span data-ttu-id="f2e4a-155">指定 SSL 流绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-155">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="f2e4a-156">此元素的类型为 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-156">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="f2e4a-157">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="f2e4a-157">\<transactionFlow></span></span>](transactionflow.md)|<span data-ttu-id="f2e4a-158">指定绑定支持事务流以及 `transactionProtocol` 属性将要使用的协议。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-158">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="f2e4a-159">此元素的类型为 <xref:System.ServiceModel.Configuration.TransactionFlowElement>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-159">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="f2e4a-160">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="f2e4a-160">\<windowsStreamSecurity></span></span>](windowsstreamsecurity.md)|<span data-ttu-id="f2e4a-161">指定自定义绑定的流安全选项。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-161">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="f2e4a-162">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-162">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f2e4a-163">父元素</span><span class="sxs-lookup"><span data-stu-id="f2e4a-163">Parent Elements</span></span>

|<span data-ttu-id="f2e4a-164">元素</span><span class="sxs-lookup"><span data-stu-id="f2e4a-164">Element</span></span>|<span data-ttu-id="f2e4a-165">描述</span><span class="sxs-lookup"><span data-stu-id="f2e4a-165">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="f2e4a-166">绑定</span><span class="sxs-lookup"><span data-stu-id="f2e4a-166">bindings</span></span>|<span data-ttu-id="f2e4a-167">包含 Windows Communication Foundation 应用程序的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-167">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f2e4a-168">备注</span><span class="sxs-lookup"><span data-stu-id="f2e4a-168">Remarks</span></span>

<span data-ttu-id="f2e4a-169">自定义绑定提供了对 WCF 消息堆栈的完全控制。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-169">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="f2e4a-170">通过添加特定实体的配置元素，可以创建特别定制的绑定。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-170">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="f2e4a-171">例如，用户可以合并 `httpsTransport` 节、`reliableSession` 节和 `security` 节以创建一个安全可靠的基于 https 的绑定。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-171">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="f2e4a-172">单个绑定按照堆栈元素在堆栈上出现的顺序来指定它们的配置元素，从而定义消息堆栈。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-172">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="f2e4a-173">每个元素都定义和配置了该堆栈的一个元素。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-173">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="f2e4a-174">在每个自定义绑定中，必须有且只能有一个传输元素。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-174">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="f2e4a-175">如果没有该元素，消息堆栈将是不完整的。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-175">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="f2e4a-176">元素在堆栈中出现的顺序非常重要，因为在将操作应用于消息时会采用该顺序。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-176">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="f2e4a-177">建议的堆栈元素顺序如下：</span><span class="sxs-lookup"><span data-stu-id="f2e4a-177">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="f2e4a-178">事务（可选）</span><span class="sxs-lookup"><span data-stu-id="f2e4a-178">Transactions (optional)</span></span>

2. <span data-ttu-id="f2e4a-179">可靠消息（可选）</span><span class="sxs-lookup"><span data-stu-id="f2e4a-179">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="f2e4a-180">安全（可选）</span><span class="sxs-lookup"><span data-stu-id="f2e4a-180">Security (optional)</span></span>

4. <span data-ttu-id="f2e4a-181">传输</span><span class="sxs-lookup"><span data-stu-id="f2e4a-181">Transport</span></span>

5. <span data-ttu-id="f2e4a-182">编码器（可选）</span><span class="sxs-lookup"><span data-stu-id="f2e4a-182">Encoder (optional)</span></span>

<span data-ttu-id="f2e4a-183">当系统提供的某个绑定不符合服务需求时，应使用自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-183">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="f2e4a-184">例如，自定义绑定可用于实现在服务终结点使用新的传输或新的编码器。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-184">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="f2e4a-185">自定义绑定是使用以特定顺序“堆叠”的绑定元素集合中的某个 <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> 构造的，顺序如下：</span><span class="sxs-lookup"><span data-stu-id="f2e4a-185">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="f2e4a-186">最顶层是一个允许流事务的可选 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-186">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="f2e4a-187">接下来是一个可选的 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>，它提供了 WS-ReliableMessaging 规范中定义的会话和排序机制。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-187">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="f2e4a-188">此会话概念可跨 SOAP 和传输中介。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-188">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="f2e4a-189">接下来是一个可选的安全绑定元素，它提供了授权、身份验证、保护和机密性之类的安全功能。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-189">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="f2e4a-190">Windows Communication Foundation （WCF）提供以下安全绑定元素：</span><span class="sxs-lookup"><span data-stu-id="f2e4a-190">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="f2e4a-191">接着是由下面的绑定元素指定的多个可选消息模式：</span><span class="sxs-lookup"><span data-stu-id="f2e4a-191">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="f2e4a-192">再下面是以下可选的传输升级/帮助器绑定元素：</span><span class="sxs-lookup"><span data-stu-id="f2e4a-192">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="f2e4a-193">再接下来是一个必需的消息编码绑定元素。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-193">Next is a required message encoding binding element.</span></span> <span data-ttu-id="f2e4a-194">可以使用自己的传输或者使用以下消息编码绑定之一：</span><span class="sxs-lookup"><span data-stu-id="f2e4a-194">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="f2e4a-195">底层是一个必需的传输元素。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-195">At the bottom is a required transport element.</span></span> <span data-ttu-id="f2e4a-196">你可以使用自己的传输，或者使用 Windows Communication Foundation （WCF）提供的传输绑定元素之一：</span><span class="sxs-lookup"><span data-stu-id="f2e4a-196">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="f2e4a-197">下表总结了每层的选项。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-197">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="f2e4a-198">层</span><span class="sxs-lookup"><span data-stu-id="f2e4a-198">Layer</span></span>|<span data-ttu-id="f2e4a-199">选项</span><span class="sxs-lookup"><span data-stu-id="f2e4a-199">Options</span></span>|<span data-ttu-id="f2e4a-200">必填</span><span class="sxs-lookup"><span data-stu-id="f2e4a-200">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="f2e4a-201">事务流</span><span class="sxs-lookup"><span data-stu-id="f2e4a-201">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="f2e4a-202">No</span><span class="sxs-lookup"><span data-stu-id="f2e4a-202">No</span></span>|
|<span data-ttu-id="f2e4a-203">可靠性</span><span class="sxs-lookup"><span data-stu-id="f2e4a-203">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="f2e4a-204">No</span><span class="sxs-lookup"><span data-stu-id="f2e4a-204">No</span></span>|
|<span data-ttu-id="f2e4a-205">安全性</span><span class="sxs-lookup"><span data-stu-id="f2e4a-205">Security</span></span>|<span data-ttu-id="f2e4a-206">对称、非对称、传输级</span><span class="sxs-lookup"><span data-stu-id="f2e4a-206">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="f2e4a-207">No</span><span class="sxs-lookup"><span data-stu-id="f2e4a-207">No</span></span>|
|<span data-ttu-id="f2e4a-208">形状更改</span><span class="sxs-lookup"><span data-stu-id="f2e4a-208">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="f2e4a-209">No</span><span class="sxs-lookup"><span data-stu-id="f2e4a-209">No</span></span>|
|<span data-ttu-id="f2e4a-210">传输升级</span><span class="sxs-lookup"><span data-stu-id="f2e4a-210">Transport Upgrades</span></span>|<span data-ttu-id="f2e4a-211">SSL 流、Windows 流、对等解析程序</span><span class="sxs-lookup"><span data-stu-id="f2e4a-211">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="f2e4a-212">No</span><span class="sxs-lookup"><span data-stu-id="f2e4a-212">No</span></span>|
|<span data-ttu-id="f2e4a-213">编码</span><span class="sxs-lookup"><span data-stu-id="f2e4a-213">Encoding</span></span>|<span data-ttu-id="f2e4a-214">文本、二进制、MTOM、自定义</span><span class="sxs-lookup"><span data-stu-id="f2e4a-214">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="f2e4a-215">是</span><span class="sxs-lookup"><span data-stu-id="f2e4a-215">Yes</span></span>|
|<span data-ttu-id="f2e4a-216">传输</span><span class="sxs-lookup"><span data-stu-id="f2e4a-216">Transport</span></span>|<span data-ttu-id="f2e4a-217">TCP、命名管道、HTTP、HTTPS、MSMQ 风格、自定义</span><span class="sxs-lookup"><span data-stu-id="f2e4a-217">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="f2e4a-218">是</span><span class="sxs-lookup"><span data-stu-id="f2e4a-218">Yes</span></span>|

<span data-ttu-id="f2e4a-219">此外，可以定义自己的绑定元素，并将它们插在前面定义的任何层之间。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-219">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="f2e4a-220">有关如何使用自定义绑定来修改系统提供的绑定的讨论，请参阅[如何：自定义系统提供的绑定](../../../wcf/extending/how-to-customize-a-system-provided-binding.md)。</span><span class="sxs-lookup"><span data-stu-id="f2e4a-220">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2e4a-221">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2e4a-221">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f2e4a-222">\<binding></span><span class="sxs-lookup"><span data-stu-id="f2e4a-222">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="f2e4a-223">绑定</span><span class="sxs-lookup"><span data-stu-id="f2e4a-223">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f2e4a-224">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="f2e4a-224">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f2e4a-225">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="f2e4a-225">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f2e4a-226">customBinding 元素</span><span class="sxs-lookup"><span data-stu-id="f2e4a-226">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="f2e4a-227">绑定</span><span class="sxs-lookup"><span data-stu-id="f2e4a-227">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f2e4a-228">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="f2e4a-228">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f2e4a-229">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="f2e4a-229">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
