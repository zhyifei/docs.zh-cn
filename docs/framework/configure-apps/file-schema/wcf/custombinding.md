---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: 60ce3cdfd7c78d152c71cdd652532cc96a6be296
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2019
ms.locfileid: "59481114"
---
# <a name="custombinding"></a><span data-ttu-id="0e3dd-101">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0e3dd-101">\<customBinding></span></span>

<span data-ttu-id="0e3dd-102">提供了对用户消息堆栈的完全控制。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="0e3dd-103">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="0e3dd-103">\<system.serviceModel>\\</span></span>
<span data-ttu-id="0e3dd-104">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="0e3dd-104">\<bindings>\\</span></span>
<span data-ttu-id="0e3dd-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0e3dd-105">\<customBinding></span></span>

## <a name="syntax"></a><span data-ttu-id="0e3dd-106">语法</span><span class="sxs-lookup"><span data-stu-id="0e3dd-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="0e3dd-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0e3dd-107">Attributes and Elements</span></span>

<span data-ttu-id="0e3dd-108">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-108">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="0e3dd-109">特性</span><span class="sxs-lookup"><span data-stu-id="0e3dd-109">Attributes</span></span>

|<span data-ttu-id="0e3dd-110">特性</span><span class="sxs-lookup"><span data-stu-id="0e3dd-110">Attribute</span></span>|<span data-ttu-id="0e3dd-111">描述</span><span class="sxs-lookup"><span data-stu-id="0e3dd-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0e3dd-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="0e3dd-112">closeTimeout</span></span>|<span data-ttu-id="0e3dd-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="0e3dd-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0e3dd-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-115">The default is 00:01:00.</span></span>|
|<span data-ttu-id="0e3dd-116">name</span><span class="sxs-lookup"><span data-stu-id="0e3dd-116">name</span></span>|<span data-ttu-id="0e3dd-117">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-117">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="0e3dd-118">此值是用户定义的一个字符串，可充当自定义绑定的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-118">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="0e3dd-119">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="0e3dd-120">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="0e3dd-121">openTimeout</span><span class="sxs-lookup"><span data-stu-id="0e3dd-121">openTimeout</span></span>|<span data-ttu-id="0e3dd-122">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="0e3dd-123">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0e3dd-124">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="0e3dd-125">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="0e3dd-125">receiveTimeout</span></span>|<span data-ttu-id="0e3dd-126">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="0e3dd-127">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0e3dd-128">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-128">The default is 00:01:00.</span></span>|
|<span data-ttu-id="0e3dd-129">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="0e3dd-129">sendTimeout</span></span>|<span data-ttu-id="0e3dd-130">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-130">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="0e3dd-131">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-131">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0e3dd-132">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-132">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0e3dd-133">子元素</span><span class="sxs-lookup"><span data-stu-id="0e3dd-133">Child Elements</span></span>

|<span data-ttu-id="0e3dd-134">元素</span><span class="sxs-lookup"><span data-stu-id="0e3dd-134">Element</span></span>|<span data-ttu-id="0e3dd-135">描述</span><span class="sxs-lookup"><span data-stu-id="0e3dd-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e3dd-136">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="0e3dd-136">\<compositeDuplex></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)|<span data-ttu-id="0e3dd-137">对自定义绑定指定双向消息处理。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-137">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="0e3dd-138">它与本身不允许进行双工通信的传输（例如，HTTP）一起使用。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-138">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="0e3dd-139">与此相反，TCP 本身允许进行双工通信，并且不要求服务在将消息发送回客户端时使用此绑定元素。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-139">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="0e3dd-140">客户端必须公开一个地址，以便服务进行联系和建立连接。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-140">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="0e3dd-141">此客户端地址由 `ClientBaseAddress` 属性提供。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-141">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="0e3dd-142">此元素的类型为 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-142">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="0e3dd-143">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="0e3dd-143">\<pnrpPeerResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/pnrppeerresolver.md)|<span data-ttu-id="0e3dd-144">指定对等名称解析协议 (PNRP) 对等名称解析程序。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-144">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="0e3dd-145">此元素的类型为 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-145">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="0e3dd-146">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="0e3dd-146">\<reliableSession></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md)|<span data-ttu-id="0e3dd-147">指定 WS-ReliableMessaging 的设置。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-147">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="0e3dd-148">如果将该元素添加到自定义绑定，则生成的通道可支持一次性传递保证。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-148">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="0e3dd-149">此元素的类型为 <xref:System.ServiceModel.Configuration.ReliableSessionElement>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-149">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="0e3dd-150">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="0e3dd-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="0e3dd-151">指定自定义绑定的安全选项。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-151">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="0e3dd-152">此元素的类型为 <xref:System.ServiceModel.Configuration.SecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-152">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="0e3dd-153">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="0e3dd-153">\<sslStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)|<span data-ttu-id="0e3dd-154">指定 SSL 流绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-154">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="0e3dd-155">此元素的类型为 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-155">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="0e3dd-156">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="0e3dd-156">\<transactionFlow></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md)|<span data-ttu-id="0e3dd-157">指定绑定支持事务流以及 `transactionProtocol` 属性将要使用的协议。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-157">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="0e3dd-158">此元素的类型为 <xref:System.ServiceModel.Configuration.TransactionFlowElement>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-158">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="0e3dd-159">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="0e3dd-159">\<windowsStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md)|<span data-ttu-id="0e3dd-160">指定自定义绑定的流安全选项。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-160">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="0e3dd-161">此元素的类型为 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-161">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0e3dd-162">父元素</span><span class="sxs-lookup"><span data-stu-id="0e3dd-162">Parent Elements</span></span>

|<span data-ttu-id="0e3dd-163">元素</span><span class="sxs-lookup"><span data-stu-id="0e3dd-163">Element</span></span>|<span data-ttu-id="0e3dd-164">描述</span><span class="sxs-lookup"><span data-stu-id="0e3dd-164">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="0e3dd-165">绑定</span><span class="sxs-lookup"><span data-stu-id="0e3dd-165">bindings</span></span>|<span data-ttu-id="0e3dd-166">包含 Windows Communication Foundation 应用程序的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-166">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0e3dd-167">备注</span><span class="sxs-lookup"><span data-stu-id="0e3dd-167">Remarks</span></span>

<span data-ttu-id="0e3dd-168">自定义绑定提供了对 WCF 消息堆栈的完全控制。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-168">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="0e3dd-169">通过添加特定实体的配置元素，可以创建特别定制的绑定。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-169">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="0e3dd-170">例如，用户可以合并 `httpsTransport` 节、`reliableSession` 节和 `security` 节以创建一个安全可靠的基于 https 的绑定。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-170">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="0e3dd-171">单个绑定按照堆栈元素在堆栈上出现的顺序来指定它们的配置元素，从而定义消息堆栈。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-171">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="0e3dd-172">每个元素都定义和配置了该堆栈的一个元素。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-172">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="0e3dd-173">在每个自定义绑定中，必须有且只能有一个传输元素。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-173">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="0e3dd-174">如果没有该元素，消息堆栈将是不完整的。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-174">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="0e3dd-175">元素在堆栈中出现的顺序非常重要，因为在将操作应用于消息时会采用该顺序。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-175">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="0e3dd-176">建议的堆栈元素顺序如下：</span><span class="sxs-lookup"><span data-stu-id="0e3dd-176">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="0e3dd-177">事务（可选）</span><span class="sxs-lookup"><span data-stu-id="0e3dd-177">Transactions (optional)</span></span>

2. <span data-ttu-id="0e3dd-178">可靠消息（可选）</span><span class="sxs-lookup"><span data-stu-id="0e3dd-178">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="0e3dd-179">安全（可选）</span><span class="sxs-lookup"><span data-stu-id="0e3dd-179">Security (optional)</span></span>

4. <span data-ttu-id="0e3dd-180">传输</span><span class="sxs-lookup"><span data-stu-id="0e3dd-180">Transport</span></span>

5. <span data-ttu-id="0e3dd-181">编码器（可选）</span><span class="sxs-lookup"><span data-stu-id="0e3dd-181">Encoder (optional)</span></span>

<span data-ttu-id="0e3dd-182">当系统提供的某个绑定不符合服务需求时，应使用自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-182">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="0e3dd-183">例如，自定义绑定可用于实现在服务终结点使用新的传输或新的编码器。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-183">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="0e3dd-184">自定义绑定是使用以特定顺序“堆叠”的绑定元素集合中的某个 <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> 构造的，顺序如下：</span><span class="sxs-lookup"><span data-stu-id="0e3dd-184">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="0e3dd-185">最顶层是一个允许流事务的可选 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-185">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="0e3dd-186">接下来是一个可选的 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>，它提供了 WS-ReliableMessaging 规范中定义的会话和排序机制。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-186">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="0e3dd-187">此会话概念可跨 SOAP 和传输中介。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-187">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="0e3dd-188">接下来是一个可选的安全绑定元素，它提供了授权、身份验证、保护和机密性之类的安全功能。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-188">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="0e3dd-189">以下安全绑定元素提供了由 Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="0e3dd-189">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="0e3dd-190">接着是由下面的绑定元素指定的多个可选消息模式：</span><span class="sxs-lookup"><span data-stu-id="0e3dd-190">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="0e3dd-191">再下面是以下可选的传输升级/帮助器绑定元素：</span><span class="sxs-lookup"><span data-stu-id="0e3dd-191">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="0e3dd-192">再接下来是一个必需的消息编码绑定元素。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-192">Next is a required message encoding binding element.</span></span> <span data-ttu-id="0e3dd-193">可以使用自己的传输或者使用以下消息编码绑定之一：</span><span class="sxs-lookup"><span data-stu-id="0e3dd-193">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="0e3dd-194">底层是一个必需的传输元素。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-194">At the bottom is a required transport element.</span></span> <span data-ttu-id="0e3dd-195">可以使用自己的传输，也可以使用其中一个传输绑定元素提供通过 Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="0e3dd-195">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="0e3dd-196">下表总结了每层的选项。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-196">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="0e3dd-197">层</span><span class="sxs-lookup"><span data-stu-id="0e3dd-197">Layer</span></span>|<span data-ttu-id="0e3dd-198">选项</span><span class="sxs-lookup"><span data-stu-id="0e3dd-198">Options</span></span>|<span data-ttu-id="0e3dd-199">必需</span><span class="sxs-lookup"><span data-stu-id="0e3dd-199">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="0e3dd-200">事务流</span><span class="sxs-lookup"><span data-stu-id="0e3dd-200">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="0e3dd-201">否</span><span class="sxs-lookup"><span data-stu-id="0e3dd-201">No</span></span>|
|<span data-ttu-id="0e3dd-202">可靠性</span><span class="sxs-lookup"><span data-stu-id="0e3dd-202">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="0e3dd-203">否</span><span class="sxs-lookup"><span data-stu-id="0e3dd-203">No</span></span>|
|<span data-ttu-id="0e3dd-204">安全性</span><span class="sxs-lookup"><span data-stu-id="0e3dd-204">Security</span></span>|<span data-ttu-id="0e3dd-205">对称、非对称、传输级</span><span class="sxs-lookup"><span data-stu-id="0e3dd-205">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="0e3dd-206">否</span><span class="sxs-lookup"><span data-stu-id="0e3dd-206">No</span></span>|
|<span data-ttu-id="0e3dd-207">形状更改</span><span class="sxs-lookup"><span data-stu-id="0e3dd-207">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="0e3dd-208">否</span><span class="sxs-lookup"><span data-stu-id="0e3dd-208">No</span></span>|
|<span data-ttu-id="0e3dd-209">传输升级</span><span class="sxs-lookup"><span data-stu-id="0e3dd-209">Transport Upgrades</span></span>|<span data-ttu-id="0e3dd-210">SSL 流、Windows 流、对等解析程序</span><span class="sxs-lookup"><span data-stu-id="0e3dd-210">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="0e3dd-211">否</span><span class="sxs-lookup"><span data-stu-id="0e3dd-211">No</span></span>|
|<span data-ttu-id="0e3dd-212">编码</span><span class="sxs-lookup"><span data-stu-id="0e3dd-212">Encoding</span></span>|<span data-ttu-id="0e3dd-213">文本、二进制、MTOM、自定义</span><span class="sxs-lookup"><span data-stu-id="0e3dd-213">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="0e3dd-214">是</span><span class="sxs-lookup"><span data-stu-id="0e3dd-214">Yes</span></span>|
|<span data-ttu-id="0e3dd-215">传输</span><span class="sxs-lookup"><span data-stu-id="0e3dd-215">Transport</span></span>|<span data-ttu-id="0e3dd-216">TCP、命名管道、HTTP、HTTPS、MSMQ 风格、自定义</span><span class="sxs-lookup"><span data-stu-id="0e3dd-216">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="0e3dd-217">是</span><span class="sxs-lookup"><span data-stu-id="0e3dd-217">Yes</span></span>|

<span data-ttu-id="0e3dd-218">此外，可以定义自己的绑定元素，并将它们插在前面定义的任何层之间。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-218">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="0e3dd-219">有关如何使用的自定义绑定修改系统提供的绑定的讨论，请参阅[如何：自定义系统提供的绑定](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)。</span><span class="sxs-lookup"><span data-stu-id="0e3dd-219">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e3dd-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e3dd-220">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0e3dd-221">\<binding></span><span class="sxs-lookup"><span data-stu-id="0e3dd-221">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="0e3dd-222">绑定</span><span class="sxs-lookup"><span data-stu-id="0e3dd-222">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0e3dd-223">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="0e3dd-223">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0e3dd-224">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="0e3dd-224">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0e3dd-225">customBinding 元素</span><span class="sxs-lookup"><span data-stu-id="0e3dd-225">customBinding Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="0e3dd-226">绑定</span><span class="sxs-lookup"><span data-stu-id="0e3dd-226">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0e3dd-227">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="0e3dd-227">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0e3dd-228">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="0e3dd-228">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
