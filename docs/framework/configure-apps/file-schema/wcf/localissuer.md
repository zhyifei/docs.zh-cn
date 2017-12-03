---
title: '&lt;localIssuer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8836d9e57dd7c4d9cfdc20c5e4856e384e6d67b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="6dfee-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="6dfee-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="6dfee-103">指定要用于颁发安全令牌的本地颁发者的地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="6dfee-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="6dfee-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6dfee-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6dfee-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="6dfee-105">\<behaviors></span></span>  
<span data-ttu-id="6dfee-106">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="6dfee-106">endpointBehaviors section</span></span>  
<span data-ttu-id="6dfee-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="6dfee-107">\<behavior></span></span>  
<span data-ttu-id="6dfee-108">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="6dfee-108">\<clientCredentials></span></span>  
<span data-ttu-id="6dfee-109">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="6dfee-109">\<issuedToken></span></span>  
<span data-ttu-id="6dfee-110">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="6dfee-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dfee-111">语法</span><span class="sxs-lookup"><span data-stu-id="6dfee-111">Syntax</span></span>  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6dfee-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6dfee-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6dfee-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6dfee-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6dfee-114">特性</span><span class="sxs-lookup"><span data-stu-id="6dfee-114">Attributes</span></span>  
  
|<span data-ttu-id="6dfee-115">特性</span><span class="sxs-lookup"><span data-stu-id="6dfee-115">Attribute</span></span>|<span data-ttu-id="6dfee-116">描述</span><span class="sxs-lookup"><span data-stu-id="6dfee-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6dfee-117">address</span><span class="sxs-lookup"><span data-stu-id="6dfee-117">address</span></span>|<span data-ttu-id="6dfee-118">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="6dfee-118">Required string.</span></span> <span data-ttu-id="6dfee-119">指定本地颁发者的 URI。</span><span class="sxs-lookup"><span data-stu-id="6dfee-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="6dfee-120">绑定</span><span class="sxs-lookup"><span data-stu-id="6dfee-120">binding</span></span>|<span data-ttu-id="6dfee-121">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="6dfee-121">Optional string.</span></span> <span data-ttu-id="6dfee-122">系统提供的一个绑定。</span><span class="sxs-lookup"><span data-stu-id="6dfee-122">One of the system-provided bindings.</span></span> <span data-ttu-id="6dfee-123">有关列表，请参阅[系统提供的绑定](../../../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="6dfee-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="6dfee-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6dfee-124">bindingConfiguration</span></span>|<span data-ttu-id="6dfee-125">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="6dfee-125">Optional string.</span></span> <span data-ttu-id="6dfee-126">指定在配置文件中找到的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="6dfee-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6dfee-127">子元素</span><span class="sxs-lookup"><span data-stu-id="6dfee-127">Child Elements</span></span>  
  
|<span data-ttu-id="6dfee-128">元素</span><span class="sxs-lookup"><span data-stu-id="6dfee-128">Element</span></span>|<span data-ttu-id="6dfee-129">描述</span><span class="sxs-lookup"><span data-stu-id="6dfee-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6dfee-130">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="6dfee-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="6dfee-131">指定此本地颁发者的标识信息。</span><span class="sxs-lookup"><span data-stu-id="6dfee-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="6dfee-132">\<标头 ></span><span class="sxs-lookup"><span data-stu-id="6dfee-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="6dfee-133">地址头的集合，要正确书写本地颁发者的地址必须使用这些地址头。</span><span class="sxs-lookup"><span data-stu-id="6dfee-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="6dfee-134">可以使用 `add` 关键字向此集合添加标头。</span><span class="sxs-lookup"><span data-stu-id="6dfee-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6dfee-135">父元素</span><span class="sxs-lookup"><span data-stu-id="6dfee-135">Parent Elements</span></span>  
  
|<span data-ttu-id="6dfee-136">元素</span><span class="sxs-lookup"><span data-stu-id="6dfee-136">Element</span></span>|<span data-ttu-id="6dfee-137">描述</span><span class="sxs-lookup"><span data-stu-id="6dfee-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6dfee-138">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="6dfee-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="6dfee-139">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="6dfee-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dfee-140">备注</span><span class="sxs-lookup"><span data-stu-id="6dfee-140">Remarks</span></span>  
 <span data-ttu-id="6dfee-141">从安全令牌服务 (STS) 获取已颁发的令牌时，必须使用地址和绑定配置客户端应用程序，以将其用于与 STS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="6dfee-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="6dfee-142">如果 <xref:System.ServiceModel.WSFederationHttpBinding> 没有为安全令牌服务提供 URL，或者联合绑定的颁发者地址为 http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous 或 `null`，则客户端的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 通道使用由 `address` 和 `binding` 指定的值与 STS 进行通信，以获取颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="6dfee-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`, the client's [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="6dfee-143">配置本地颁发者的详细信息，请参阅[如何： 配置本地颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)。</span><span class="sxs-lookup"><span data-stu-id="6dfee-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dfee-144">示例</span><span class="sxs-lookup"><span data-stu-id="6dfee-144">Example</span></span>  
 <span data-ttu-id="6dfee-145">下面的示例设置 `address` 元素的 `binding`、`bindingConfiguration` 和 `localIssuer` 属性。</span><span class="sxs-lookup"><span data-stu-id="6dfee-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6dfee-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dfee-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="6dfee-147">安全行为</span><span class="sxs-lookup"><span data-stu-id="6dfee-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="6dfee-148">如何： 配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="6dfee-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="6dfee-149">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="6dfee-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="6dfee-150">安全行为</span><span class="sxs-lookup"><span data-stu-id="6dfee-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="6dfee-151">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="6dfee-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="6dfee-152">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="6dfee-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="6dfee-153">保护客户端</span><span class="sxs-lookup"><span data-stu-id="6dfee-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="6dfee-154">如何： 创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="6dfee-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="6dfee-155">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="6dfee-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
