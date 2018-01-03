---
title: "WSTrustChannelFactory 和 WSTrustChannel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cec467-e963-4132-b18b-7d0b3a2e979f
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 35f4449f7a826ea49be750cd750cb989c8c455fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wstrustchannelfactory-and-wstrustchannel"></a><span data-ttu-id="8aefa-102">WSTrustChannelFactory 和 WSTrustChannel</span><span class="sxs-lookup"><span data-stu-id="8aefa-102">WSTrustChannelFactory and WSTrustChannel</span></span>
<span data-ttu-id="8aefa-103">如果已熟悉 Windows Communication Foundation (WCF)，便知道 WCF 客户端已可感知联合。</span><span class="sxs-lookup"><span data-stu-id="8aefa-103">If you are already familiar with Windows Communication Foundation (WCF), you know that a WCF client is already federation aware.</span></span> <span data-ttu-id="8aefa-104">通过使用 <xref:System.ServiceModel.WSFederationHttpBinding> 或相似的自定义绑定配置 WCF 客户端，便可对服务启用联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="8aefa-104">By configuring a WCF client with a <xref:System.ServiceModel.WSFederationHttpBinding> or similar custom binding, you can enable federated authentication to a service.</span></span>  
  
 <span data-ttu-id="8aefa-105">WCF 获取由后台安全令牌服务 (STS) 颁发的令牌，并使用此令牌对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8aefa-105">WCF obtains the token that is issued by the security token service (STS) behind the scenes and uses this token to authenticate to the service.</span></span> <span data-ttu-id="8aefa-106">此方法的主要限制在于无法查看客户端与服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="8aefa-106">The main limitation to this approach is that there is no visibility into the client’s communications with the server.</span></span> <span data-ttu-id="8aefa-107">WCF 基于在绑定上颁发的令牌参数，自动生成 STS 的请求安全令牌 (RST)。</span><span class="sxs-lookup"><span data-stu-id="8aefa-107">WCF automatically generates the request security token (RST) to the STS based on the issued token parameters on the binding.</span></span> <span data-ttu-id="8aefa-108">这意味着客户端不能改变每个请求的 RST 参数、无法通过检查请求安全令牌响应 (RSTR) 获取显示声明等信息，也不能缓存令牌供将来使用。</span><span class="sxs-lookup"><span data-stu-id="8aefa-108">This means that the client cannot vary the RST parameters per request, inspect the request security token response (RSTR) to get information such as display claims, or cache the token for future use.</span></span>  
  
 <span data-ttu-id="8aefa-109">目前，WCF 客户端适用于基本联合方案。</span><span class="sxs-lookup"><span data-stu-id="8aefa-109">Currently, the WCF client is suitable for basic federation scenarios.</span></span> <span data-ttu-id="8aefa-110">然而，Windows Identity Foundation (WIF) 支持的其中一个主要方案需要对 RST 拥有 WCF 不轻易允许的级别的控制。</span><span class="sxs-lookup"><span data-stu-id="8aefa-110">However, one of the major scenarios that Windows Identity Foundation (WIF) supports requires control over the RST at a level that WCF does not easily allow.</span></span> <span data-ttu-id="8aefa-111">因此，WIF 添加了针对与 STS 的通信提供更强控制的功能。</span><span class="sxs-lookup"><span data-stu-id="8aefa-111">Therefore, WIF adds features that give you more control over communication with the STS.</span></span>  
  
 <span data-ttu-id="8aefa-112">WIF 支持以下联合方案：</span><span class="sxs-lookup"><span data-stu-id="8aefa-112">WIF supports the following federation scenarios:</span></span>  
  
-   <span data-ttu-id="8aefa-113">在没有任何 WIF 依赖项的情况下使用 WCF 客户端对联合服务进行身份验证</span><span class="sxs-lookup"><span data-stu-id="8aefa-113">Using a WCF client without any WIF dependencies to authenticate to a federated service</span></span>  
  
-   <span data-ttu-id="8aefa-114">在 WCF 客户端上启用 WIF，将 ActAs 或 OnBehalfOf 元素插入 STS 的 RST 中</span><span class="sxs-lookup"><span data-stu-id="8aefa-114">Enabling WIF on a WCF client to insert an ActAs or OnBehalfOf element into the RST to the STS</span></span>  
  
-   <span data-ttu-id="8aefa-115">仅使用 WIF 从 STS 获取令牌，然后启用 WCF 客户端，以便使用此令牌进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8aefa-115">Using WIF alone to obtain a token from the STS and then enable a WCF client to authenticate with this token.</span></span> <span data-ttu-id="8aefa-116">有关详细信息，请参阅 [ClaimsAwareWebService](http://go.microsoft.com/fwlink/?LinkID=248406) 示例。</span><span class="sxs-lookup"><span data-stu-id="8aefa-116">For more information, see [ClaimsAwareWebService](http://go.microsoft.com/fwlink/?LinkID=248406) sample.</span></span>  
  
 <span data-ttu-id="8aefa-117">第一个方案很容易理解：现有的 WCF 客户端将继续适用于 WIF 信赖方和 STS。</span><span class="sxs-lookup"><span data-stu-id="8aefa-117">The first scenario is self-explanatory: Existing WCF clients will continue to work with WIF relying parties and STSs.</span></span> <span data-ttu-id="8aefa-118">本主题讨论剩余的两个方案。</span><span class="sxs-lookup"><span data-stu-id="8aefa-118">This topic discusses the remaining two scenarios.</span></span>  
  
## <a name="enhancing-an-existing-wcf-client-with-actas--onbehalfof"></a><span data-ttu-id="8aefa-119">通过 ActAs/OnBehalfOf 增强现有的 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="8aefa-119">Enhancing an Existing WCF Client with ActAs / OnBehalfOf</span></span>  
 <span data-ttu-id="8aefa-120">在典型的标识委派方案中，客户端调用中间层服务，该服务随后调用后端服务。</span><span class="sxs-lookup"><span data-stu-id="8aefa-120">In a typical identity delegation scenario, a client calls a middle-tier service, which then calls a back-end service.</span></span> <span data-ttu-id="8aefa-121">中间层服务充当客户端或代表客户端执行操作。</span><span class="sxs-lookup"><span data-stu-id="8aefa-121">The middle-tier service acts as, or acts on behalf of, the client.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="8aefa-122">ActAs 和 OnBehalfOf 有何区别？</span><span class="sxs-lookup"><span data-stu-id="8aefa-122">What is the difference between ActAs and OnBehalfOf?</span></span>  
>   
>  <span data-ttu-id="8aefa-123">从 WS-Trust 协议的角度来看：</span><span class="sxs-lookup"><span data-stu-id="8aefa-123">From the WS-Trust procotol standpoint:</span></span>  
>   
>  1.  <span data-ttu-id="8aefa-124">ActAs RST 元素指示请求者想要的令牌包含有关两个不同实体的声明，这两个实体分别是请求者和由 ActAs 元素中的令牌表示的外部实体。</span><span class="sxs-lookup"><span data-stu-id="8aefa-124">An ActAs RST element indicates that the requestor wants a token that contains claims about two distinct entities: the requestor, and an external entity represented by the token in the ActAs element.</span></span>  
> 2.  <span data-ttu-id="8aefa-125">OnBehalfOf RST 元素指示请求者想要的令牌包含仅与一个实体有关的声明，这个实体是由 OnBehalfOf 元素中的令牌表示的外部实体。</span><span class="sxs-lookup"><span data-stu-id="8aefa-125">An OnBehalfOf RST element indicates that the requestor wants a token that contains claims only about one entity: the external entity represented by the token in the OnBehalfOf element.</span></span>  
>   
>  <span data-ttu-id="8aefa-126">ActAs 功能通常用于需要复合委派的方案，其中所颁发令牌的最终接收方可以检查整个委派链，可以查看客户端和所有中介。</span><span class="sxs-lookup"><span data-stu-id="8aefa-126">The ActAs feature is typically used in scenarios that require composite delegation, where the final recipient of the issued token can inspect the entire delegation chain and see not just the client, but all intermediaries.</span></span> <span data-ttu-id="8aefa-127">这样，它可以基于整个标识委派链执行访问控制、审核和其他相关活动。</span><span class="sxs-lookup"><span data-stu-id="8aefa-127">This lets it perform access control, auditing and other related activities based on the entire identity delegation chain.</span></span> <span data-ttu-id="8aefa-128">ActAs 功能通常用于在多层系统中进行身份验证以及在层之间传递有关标识的信息（无需在应用程序/业务逻辑层传递此信息）。</span><span class="sxs-lookup"><span data-stu-id="8aefa-128">The ActAs feature is commonly used in multi-tiered systems to authenticate and pass information about identities between the tiers without having to pass this information at the application/business logic layer.</span></span>  
>   
>  <span data-ttu-id="8aefa-129">OnBehalfOf 功能用于仅原始客户端的标识重要并且与 Windows 中可用的标识模拟功能同样高效的情况。</span><span class="sxs-lookup"><span data-stu-id="8aefa-129">The OnBehalfOf feature is used in scenarios where only the identity of the original client is important and is effectively the same as the identity impersonation feature available in Windows.</span></span> <span data-ttu-id="8aefa-130">使用 OnBehalfOf 时，所颁发令牌的最终接收方只能查看有关原始客户端的声明，未保留有关中介的信息。</span><span class="sxs-lookup"><span data-stu-id="8aefa-130">When OnBehalfOf is used, the final recipient of the issued token can only see claims about the original client, and the information about intermediaries is not preserved.</span></span> <span data-ttu-id="8aefa-131">使用 OnBehalfOf 功能的常见模式是代理模式，在此模式中，客户端无法直接访问 STS，但可以通过代理网关通信。</span><span class="sxs-lookup"><span data-stu-id="8aefa-131">One common pattern where the OnBehalfOf feature is used is the proxy pattern where the client cannot access the STS directly but instead communicates through a proxy gateway.</span></span> <span data-ttu-id="8aefa-132">代理网关对调用方进行身份验证并将有关调用方的信息放入 RST 消息的 OnBehalfOf 元素中，然后将该消息发送到真正的 STS 中以供处理。</span><span class="sxs-lookup"><span data-stu-id="8aefa-132">The proxy gateway authenticates the caller and puts information about the caller into the OnBehalfOf element of the RST message that it then sends to the real STS for processing.</span></span> <span data-ttu-id="8aefa-133">生成的令牌仅包含与代理的客户端有关的声明，因此此代理对所颁发令牌的接收方来说完全透明。请注意，WIF 不支持 \<wsse:SecurityTokenReference> 或 \<wsa:EndpointReferences> 作为 \<wst:OnBehalfOf> 的子级。</span><span class="sxs-lookup"><span data-stu-id="8aefa-133">The resulting token contains only claims related to the client of the proxy, making the proxy completely transparent to the receiver of the issued token.Note that WIF does not support \<wsse:SecurityTokenReference> or \<wsa:EndpointReferences> as a child of \<wst:OnBehalfOf>.</span></span> <span data-ttu-id="8aefa-134">WS-Trust 规范允许三种标识原始请求者（代理代表其执行操作）的方法。</span><span class="sxs-lookup"><span data-stu-id="8aefa-134">The WS-Trust specification allows for three ways to identify the original requestor (on behalf of whom the proxy is acting).</span></span> <span data-ttu-id="8aefa-135">这些是：</span><span class="sxs-lookup"><span data-stu-id="8aefa-135">These are:</span></span>  
>   
>  -   <span data-ttu-id="8aefa-136">安全令牌引用。</span><span class="sxs-lookup"><span data-stu-id="8aefa-136">Security token reference.</span></span> <span data-ttu-id="8aefa-137">对令牌的引用（消息中的引用，或者可能是带外检索的引用）。</span><span class="sxs-lookup"><span data-stu-id="8aefa-137">A reference to a token, either in the message, or possibly retrieved out of band).</span></span>  
> -   <span data-ttu-id="8aefa-138">终结点引用。</span><span class="sxs-lookup"><span data-stu-id="8aefa-138">Endpoint reference.</span></span> <span data-ttu-id="8aefa-139">作为查找数据的密钥使用（仍为带外）。</span><span class="sxs-lookup"><span data-stu-id="8aefa-139">Used as a key to look up data, again out of band.</span></span>  
> -   <span data-ttu-id="8aefa-140">安全令牌。</span><span class="sxs-lookup"><span data-stu-id="8aefa-140">Security token.</span></span> <span data-ttu-id="8aefa-141">直接标识原始请求方。</span><span class="sxs-lookup"><span data-stu-id="8aefa-141">Identifies the original requestor directly.</span></span>  
>   
>  <span data-ttu-id="8aefa-142">WIF 仅支持安全令牌（加密或未加密）作为 \<wst:OnBehalfOf> 的直接子元素。</span><span class="sxs-lookup"><span data-stu-id="8aefa-142">WIF supports only security tokens, either encrypted or unencrypted, as a direct child element of \<wst:OnBehalfOf>.</span></span>  
  
 <span data-ttu-id="8aefa-143">使用 RST 中的 ActAs 和 OnBehalfOf 令牌元素将此信息传达给 WS-Trust 颁发者。</span><span class="sxs-lookup"><span data-stu-id="8aefa-143">This information is conveyed to a WS-Trust issuer using the ActAs and OnBehalfOf token elements in the RST.</span></span>  
  
 <span data-ttu-id="8aefa-144">WCF 在允许将任意 XML 元素添加到 RST 的绑定上公开扩展点。</span><span class="sxs-lookup"><span data-stu-id="8aefa-144">WCF exposes an extensibility point on the binding that allows arbitrary XML elements to be added to the RST.</span></span> <span data-ttu-id="8aefa-145">然而，因为扩展点与该绑定关联，所以每次调用都需要改变 RST 内容的方案必须在每次调用时重新创建客户端，这将降低性能。</span><span class="sxs-lookup"><span data-stu-id="8aefa-145">However, because the extensibility point is tied to the binding, scenarios that require the RST contents to vary per call must re-create the client for every call, which decreases performance.</span></span> <span data-ttu-id="8aefa-146">WIF 使用 `ChannelFactory` 类上的扩展方法，因此开发人员可以将带外获取的任何令牌附加到 RST。</span><span class="sxs-lookup"><span data-stu-id="8aefa-146">WIF uses extension methods on the `ChannelFactory` class to allow developers to attach any token that is obtained out of band to the RST.</span></span> <span data-ttu-id="8aefa-147">下方的代码示例演示如何获取表示客户端（例如 X.509、用户名或安全断言标记语言 (SAML) 令牌）的令牌并将它附加到发送给颁发者的 RST。</span><span class="sxs-lookup"><span data-stu-id="8aefa-147">The following code example shows how to take a token that represents the client (such as an X.509, username, or Security Assertion Markup Language (SAML) token) and attach it to the RST that is sent to the issuer.</span></span>  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelActingAs<IHelloService>( clientSamlToken );  
serviceChannel.Hello("Hi!");  
```  
  
 <span data-ttu-id="8aefa-148">WIF 提供如下优点：</span><span class="sxs-lookup"><span data-stu-id="8aefa-148">WIF provides the following benefits:</span></span>  
  
-   <span data-ttu-id="8aefa-149">可以按通道修改 RST；因此，中间层服务不需要为每个客户端重新创建通道工厂，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="8aefa-149">The RST can be modified per channel; therefore, middle-tier services do not have to re-create the channel factory for each client, which improves performance.</span></span>  
  
-   <span data-ttu-id="8aefa-150">这适用于现有的 WCF 客户端，可能为要启用标识委派语义的现有 WCF 中间层服务提供简单的升级路径。</span><span class="sxs-lookup"><span data-stu-id="8aefa-150">This works with existing WCF clients, which makes an easy upgrade path possible for existing WCF middle-tier services that want to enable identity delegation semantics.</span></span>  
  
 <span data-ttu-id="8aefa-151">然而，仍看不到客户端与 STS 之间的通信。</span><span class="sxs-lookup"><span data-stu-id="8aefa-151">However, there is still no visibility into the client’s communication with the STS.</span></span> <span data-ttu-id="8aefa-152">我们将在第三个方案中查看此问题。</span><span class="sxs-lookup"><span data-stu-id="8aefa-152">We’ll examine this in the third scenario.</span></span>  
  
## <a name="communicating-directly-with-an-issuer-and-using-the-issued-token-to-authenticate"></a><span data-ttu-id="8aefa-153">与颁发者直接通信并使用颁发的令牌进行身份验证</span><span class="sxs-lookup"><span data-stu-id="8aefa-153">Communicating Directly with an Issuer and Using the Issued Token to Authenticate</span></span>  
 <span data-ttu-id="8aefa-154">对于某些高级方案，增强 WCF 客户端是不够的。</span><span class="sxs-lookup"><span data-stu-id="8aefa-154">For some advanced scenarios, enhancing a WCF client is not enough.</span></span> <span data-ttu-id="8aefa-155">仅使用 WCF 的开发人员通常使用 Message In/Message Out 协定，手动处理颁发者响应的客户端分析。</span><span class="sxs-lookup"><span data-stu-id="8aefa-155">Developers who use only WCF typically use Message In / Message Out contracts and handle client-side parsing of the issuer response manually.</span></span>  
  
 <span data-ttu-id="8aefa-156">WIF 引入了 <xref:System.ServiceModel.Security.WSTrustChannelFactory> 和 <xref:System.ServiceModel.Security.WSTrustChannel> 类，使客户端直接与 WS-Trust 颁发者通信。</span><span class="sxs-lookup"><span data-stu-id="8aefa-156">WIF introduces the <xref:System.ServiceModel.Security.WSTrustChannelFactory> and <xref:System.ServiceModel.Security.WSTrustChannel> classes to let the client communicate directly with a WS-Trust issuer.</span></span> <span data-ttu-id="8aefa-157">通过 <xref:System.ServiceModel.Security.WSTrustChannelFactory> 和 <xref:System.ServiceModel.Security.WSTrustChannel> 类，强类型 RST 和 RSTR 对象可在客户端和颁发者之间流动，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="8aefa-157">The <xref:System.ServiceModel.Security.WSTrustChannelFactory> and <xref:System.ServiceModel.Security.WSTrustChannel> classes enable strongly typed RST and RSTR objects to flow between the client and issuer, as shown in the following code example.</span></span>  
  
```  
WSTrustChannelFactory trustChannelFactory = new WSTrustChannelFactory( stsBinding, stsAddress );  
WSTrustChannel channel = (WSTrustChannel) trustChannelFactory.CreateChannel();  
RequestSecurityToken rst = new RequestSecurityToken(RequestTypes.Issue);  
rst.AppliesTo = new EndpointAddress(serviceAddress);  
RequestSecurityTokenResponse rstr = null;  
SecurityToken token = channel.Issue(rst, out rstr);  
```  
  
 <span data-ttu-id="8aefa-158">请注意，<xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> 方法上的 `out` 参数允许访问 RSTR 进行客户端检查。</span><span class="sxs-lookup"><span data-stu-id="8aefa-158">Note that the `out` parameter on the <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> method allows access to the RSTR for client-side inspection.</span></span>  
  
 <span data-ttu-id="8aefa-159">至此，我们仅了解到如何获取令牌。</span><span class="sxs-lookup"><span data-stu-id="8aefa-159">So far, we’ve only seen how to obtain a token.</span></span> <span data-ttu-id="8aefa-160">从 <xref:System.ServiceModel.Security.WSTrustChannel> 对象返回的令牌是 `GenericXmlSecurityToken`，其中包含对信赖方进行身份验证所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="8aefa-160">The token that is returned from the <xref:System.ServiceModel.Security.WSTrustChannel> object is a `GenericXmlSecurityToken` that contains all of the information that is necessary for authentication to a relying party.</span></span> <span data-ttu-id="8aefa-161">下方的代码示例演示如何使用此令牌。</span><span class="sxs-lookup"><span data-stu-id="8aefa-161">The following code example shows how to use this token.</span></span>  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelWithIssuedToken<IHelloService>( token ); serviceChannel.Hello("Hi!");  
```  
  
 <span data-ttu-id="8aefa-162">`ChannelFactory` 对象上的 <xref:System.ServiceModel.ChannelFactory%601.CreateChannelWithIssuedToken%2A> 扩展方法会让 WIF 知道你已在带外获取令牌，且它应该停止对颁发者的常规 WCF 调用，而改用你所获取的令牌对信赖方进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8aefa-162">The <xref:System.ServiceModel.ChannelFactory%601.CreateChannelWithIssuedToken%2A> extension method on the `ChannelFactory` object indicates to WIF that you have obtained a token out of band, and that it should stop the normal WCF call to the issuer and instead use the token that you obtained to authenticate to the relying party.</span></span> <span data-ttu-id="8aefa-163">这具有如下优点：</span><span class="sxs-lookup"><span data-stu-id="8aefa-163">This has the following benefits:</span></span>  
  
-   <span data-ttu-id="8aefa-164">可以完全控制令牌颁发进程。</span><span class="sxs-lookup"><span data-stu-id="8aefa-164">It gives you complete control over the token issuance process.</span></span>  
  
-   <span data-ttu-id="8aefa-165">通过直接在传出 RST 上设置这些属性来支持 ActAs/OnBehalfOf 方案。</span><span class="sxs-lookup"><span data-stu-id="8aefa-165">It supports ActAs / OnBehalfOf scenarios by directly setting these properties on the outgoing RST.</span></span>  
  
-   <span data-ttu-id="8aefa-166">可以基于 RSTR 的内容做出动态客户端信任决策。</span><span class="sxs-lookup"><span data-stu-id="8aefa-166">It enables dynamic client-side trust decisions to be made based on the contents of the RSTR.</span></span>  
  
-   <span data-ttu-id="8aefa-167">可以缓存并重新使用从 <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> 方法返回的令牌。</span><span class="sxs-lookup"><span data-stu-id="8aefa-167">It lets you cache and reuse the token that is returned from the <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> method.</span></span>  
  
-   <span data-ttu-id="8aefa-168">可根据 WCF 最佳做法通过 <xref:System.ServiceModel.Security.WSTrustChannelFactory> 和 <xref:System.ServiceModel.Security.WSTrustChannel> 控制通道缓存、错误和恢复语义。</span><span class="sxs-lookup"><span data-stu-id="8aefa-168"><xref:System.ServiceModel.Security.WSTrustChannelFactory> and <xref:System.ServiceModel.Security.WSTrustChannel> allow for control of channel caching, fault, and recovery semantics according to WCF best practices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aefa-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="8aefa-169">See Also</span></span>  
 [<span data-ttu-id="8aefa-170">WIF 功能</span><span class="sxs-lookup"><span data-stu-id="8aefa-170">WIF Features</span></span>](../../../docs/framework/security/wif-features.md)
