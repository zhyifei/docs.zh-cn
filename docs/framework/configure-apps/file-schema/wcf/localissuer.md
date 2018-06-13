---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9118d1462d4790bb457fc8dc2f7c74b6e69de43a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749109"
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="0f2be-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="0f2be-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="0f2be-103">指定要用于颁发安全令牌的本地颁发者的地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="0f2be-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="0f2be-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0f2be-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0f2be-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="0f2be-105">\<behaviors></span></span>  
<span data-ttu-id="0f2be-106">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="0f2be-106">endpointBehaviors section</span></span>  
<span data-ttu-id="0f2be-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="0f2be-107">\<behavior></span></span>  
<span data-ttu-id="0f2be-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0f2be-108">\<clientCredentials></span></span>  
<span data-ttu-id="0f2be-109">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="0f2be-109">\<issuedToken></span></span>  
<span data-ttu-id="0f2be-110">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="0f2be-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f2be-111">语法</span><span class="sxs-lookup"><span data-stu-id="0f2be-111">Syntax</span></span>  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f2be-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0f2be-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0f2be-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0f2be-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f2be-114">特性</span><span class="sxs-lookup"><span data-stu-id="0f2be-114">Attributes</span></span>  
  
|<span data-ttu-id="0f2be-115">特性</span><span class="sxs-lookup"><span data-stu-id="0f2be-115">Attribute</span></span>|<span data-ttu-id="0f2be-116">描述</span><span class="sxs-lookup"><span data-stu-id="0f2be-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f2be-117">address</span><span class="sxs-lookup"><span data-stu-id="0f2be-117">address</span></span>|<span data-ttu-id="0f2be-118">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="0f2be-118">Required string.</span></span> <span data-ttu-id="0f2be-119">指定本地颁发者的 URI。</span><span class="sxs-lookup"><span data-stu-id="0f2be-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="0f2be-120">绑定</span><span class="sxs-lookup"><span data-stu-id="0f2be-120">binding</span></span>|<span data-ttu-id="0f2be-121">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="0f2be-121">Optional string.</span></span> <span data-ttu-id="0f2be-122">系统提供的一个绑定。</span><span class="sxs-lookup"><span data-stu-id="0f2be-122">One of the system-provided bindings.</span></span> <span data-ttu-id="0f2be-123">有关列表，请参阅[系统提供的绑定](../../../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="0f2be-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="0f2be-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0f2be-124">bindingConfiguration</span></span>|<span data-ttu-id="0f2be-125">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="0f2be-125">Optional string.</span></span> <span data-ttu-id="0f2be-126">指定在配置文件中找到的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="0f2be-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f2be-127">子元素</span><span class="sxs-lookup"><span data-stu-id="0f2be-127">Child Elements</span></span>  
  
|<span data-ttu-id="0f2be-128">元素</span><span class="sxs-lookup"><span data-stu-id="0f2be-128">Element</span></span>|<span data-ttu-id="0f2be-129">描述</span><span class="sxs-lookup"><span data-stu-id="0f2be-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f2be-130">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="0f2be-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="0f2be-131">指定此本地颁发者的标识信息。</span><span class="sxs-lookup"><span data-stu-id="0f2be-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="0f2be-132">\<headers></span><span class="sxs-lookup"><span data-stu-id="0f2be-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="0f2be-133">地址头的集合，要正确书写本地颁发者的地址必须使用这些地址头。</span><span class="sxs-lookup"><span data-stu-id="0f2be-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="0f2be-134">可以使用 `add` 关键字向此集合添加标头。</span><span class="sxs-lookup"><span data-stu-id="0f2be-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f2be-135">父元素</span><span class="sxs-lookup"><span data-stu-id="0f2be-135">Parent Elements</span></span>  
  
|<span data-ttu-id="0f2be-136">元素</span><span class="sxs-lookup"><span data-stu-id="0f2be-136">Element</span></span>|<span data-ttu-id="0f2be-137">描述</span><span class="sxs-lookup"><span data-stu-id="0f2be-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f2be-138">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="0f2be-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="0f2be-139">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="0f2be-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f2be-140">备注</span><span class="sxs-lookup"><span data-stu-id="0f2be-140">Remarks</span></span>  
 <span data-ttu-id="0f2be-141">从安全令牌服务 (STS) 获取已颁发的令牌时，必须使用地址和绑定配置客户端应用程序，以将其用于与 STS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="0f2be-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="0f2be-142">当<xref:System.ServiceModel.WSFederationHttpBinding>不提供的 URL 的安全令牌服务，或者联合绑定的颁发者地址为http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous或`null`，客户端的 Windows Communication Foundation (WCF) 通道使用指定的值`address`和`binding`与以获取颁发的令牌的 STS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="0f2be-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="0f2be-143">配置本地颁发者的详细信息，请参阅[如何： 配置本地颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)。</span><span class="sxs-lookup"><span data-stu-id="0f2be-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f2be-144">示例</span><span class="sxs-lookup"><span data-stu-id="0f2be-144">Example</span></span>  
 <span data-ttu-id="0f2be-145">下面的示例设置 `address` 元素的 `binding`、`bindingConfiguration` 和 `localIssuer` 属性。</span><span class="sxs-lookup"><span data-stu-id="0f2be-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f2be-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f2be-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="0f2be-147">安全行为</span><span class="sxs-lookup"><span data-stu-id="0f2be-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="0f2be-148">如何：配置本地证书颁发者</span><span class="sxs-lookup"><span data-stu-id="0f2be-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="0f2be-149">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="0f2be-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="0f2be-150">安全行为</span><span class="sxs-lookup"><span data-stu-id="0f2be-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="0f2be-151">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="0f2be-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="0f2be-152">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="0f2be-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="0f2be-153">保护客户端</span><span class="sxs-lookup"><span data-stu-id="0f2be-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="0f2be-154">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="0f2be-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="0f2be-155">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="0f2be-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
