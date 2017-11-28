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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6b11f5cbf2d70b4fff607ac42c2c98af7fb9542b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="54395-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="54395-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="54395-103">指定要用于颁发安全令牌的本地颁发者的地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="54395-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="54395-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="54395-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="54395-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="54395-105">\<behaviors></span></span>  
<span data-ttu-id="54395-106">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="54395-106">endpointBehaviors section</span></span>  
<span data-ttu-id="54395-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="54395-107">\<behavior></span></span>  
<span data-ttu-id="54395-108">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="54395-108">\<clientCredentials></span></span>  
<span data-ttu-id="54395-109">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="54395-109">\<issuedToken></span></span>  
<span data-ttu-id="54395-110">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="54395-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54395-111">语法</span><span class="sxs-lookup"><span data-stu-id="54395-111">Syntax</span></span>  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54395-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="54395-112">Attributes and Elements</span></span>  
 <span data-ttu-id="54395-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="54395-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54395-114">特性</span><span class="sxs-lookup"><span data-stu-id="54395-114">Attributes</span></span>  
  
|<span data-ttu-id="54395-115">特性</span><span class="sxs-lookup"><span data-stu-id="54395-115">Attribute</span></span>|<span data-ttu-id="54395-116">描述</span><span class="sxs-lookup"><span data-stu-id="54395-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54395-117">address</span><span class="sxs-lookup"><span data-stu-id="54395-117">address</span></span>|<span data-ttu-id="54395-118">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="54395-118">Required string.</span></span> <span data-ttu-id="54395-119">指定本地颁发者的 URI。</span><span class="sxs-lookup"><span data-stu-id="54395-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="54395-120">绑定</span><span class="sxs-lookup"><span data-stu-id="54395-120">binding</span></span>|<span data-ttu-id="54395-121">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="54395-121">Optional string.</span></span> <span data-ttu-id="54395-122">系统提供的一个绑定。</span><span class="sxs-lookup"><span data-stu-id="54395-122">One of the system-provided bindings.</span></span> <span data-ttu-id="54395-123">有关列表，请参阅[系统提供的绑定](../../../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="54395-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="54395-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="54395-124">bindingConfiguration</span></span>|<span data-ttu-id="54395-125">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="54395-125">Optional string.</span></span> <span data-ttu-id="54395-126">指定在配置文件中找到的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="54395-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54395-127">子元素</span><span class="sxs-lookup"><span data-stu-id="54395-127">Child Elements</span></span>  
  
|<span data-ttu-id="54395-128">元素</span><span class="sxs-lookup"><span data-stu-id="54395-128">Element</span></span>|<span data-ttu-id="54395-129">描述</span><span class="sxs-lookup"><span data-stu-id="54395-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54395-130">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="54395-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="54395-131">指定此本地颁发者的标识信息。</span><span class="sxs-lookup"><span data-stu-id="54395-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="54395-132">\<标头 ></span><span class="sxs-lookup"><span data-stu-id="54395-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="54395-133">地址头的集合，要正确书写本地颁发者的地址必须使用这些地址头。</span><span class="sxs-lookup"><span data-stu-id="54395-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="54395-134">可以使用 `add` 关键字向此集合添加标头。</span><span class="sxs-lookup"><span data-stu-id="54395-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54395-135">父元素</span><span class="sxs-lookup"><span data-stu-id="54395-135">Parent Elements</span></span>  
  
|<span data-ttu-id="54395-136">元素</span><span class="sxs-lookup"><span data-stu-id="54395-136">Element</span></span>|<span data-ttu-id="54395-137">描述</span><span class="sxs-lookup"><span data-stu-id="54395-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54395-138">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="54395-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="54395-139">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="54395-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54395-140">备注</span><span class="sxs-lookup"><span data-stu-id="54395-140">Remarks</span></span>  
 <span data-ttu-id="54395-141">从安全令牌服务 (STS) 获取已颁发的令牌时，必须使用地址和绑定配置客户端应用程序，以将其用于与 STS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="54395-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="54395-142">如果 <xref:System.ServiceModel.WSFederationHttpBinding> 没有为安全令牌服务提供 URL，或者联合绑定的颁发者地址为 http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous 或 `null`，则客户端的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 通道使用由 `address` 和 `binding` 指定的值与 STS 进行通信，以获取颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="54395-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`, the client's [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="54395-143">配置本地颁发者的详细信息，请参阅[如何： 配置本地颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)。</span><span class="sxs-lookup"><span data-stu-id="54395-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54395-144">示例</span><span class="sxs-lookup"><span data-stu-id="54395-144">Example</span></span>  
 <span data-ttu-id="54395-145">下面的示例设置 `address` 元素的 `binding`、`bindingConfiguration` 和 `localIssuer` 属性。</span><span class="sxs-lookup"><span data-stu-id="54395-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54395-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54395-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="54395-147">安全行为</span><span class="sxs-lookup"><span data-stu-id="54395-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="54395-148">如何： 配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="54395-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="54395-149">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="54395-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="54395-150">安全行为</span><span class="sxs-lookup"><span data-stu-id="54395-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="54395-151">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="54395-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="54395-152">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="54395-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="54395-153">保护客户端</span><span class="sxs-lookup"><span data-stu-id="54395-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="54395-154">如何： 创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="54395-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="54395-155">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="54395-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
