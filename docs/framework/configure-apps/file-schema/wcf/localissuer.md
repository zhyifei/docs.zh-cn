---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9a51387cd75d57a6828ecde1dcd788b056f7e27a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122871"
---
# <a name="localissuer"></a><span data-ttu-id="0c8ec-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="0c8ec-101">\<localIssuer></span></span>
<span data-ttu-id="0c8ec-102">指定要用于颁发安全令牌的本地颁发者的地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="0c8ec-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0c8ec-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c8ec-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0c8ec-104">\<behaviors></span></span>  
<span data-ttu-id="0c8ec-105">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="0c8ec-105">endpointBehaviors section</span></span>  
<span data-ttu-id="0c8ec-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0c8ec-106">\<behavior></span></span>  
<span data-ttu-id="0c8ec-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0c8ec-107">\<clientCredentials></span></span>  
<span data-ttu-id="0c8ec-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="0c8ec-108">\<issuedToken></span></span>  
<span data-ttu-id="0c8ec-109">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="0c8ec-109">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8ec-110">语法</span><span class="sxs-lookup"><span data-stu-id="0c8ec-110">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c8ec-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0c8ec-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0c8ec-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c8ec-113">特性</span><span class="sxs-lookup"><span data-stu-id="0c8ec-113">Attributes</span></span>  
  
|<span data-ttu-id="0c8ec-114">特性</span><span class="sxs-lookup"><span data-stu-id="0c8ec-114">Attribute</span></span>|<span data-ttu-id="0c8ec-115">描述</span><span class="sxs-lookup"><span data-stu-id="0c8ec-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c8ec-116">地址</span><span class="sxs-lookup"><span data-stu-id="0c8ec-116">address</span></span>|<span data-ttu-id="0c8ec-117">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-117">Required string.</span></span> <span data-ttu-id="0c8ec-118">指定本地颁发者的 URI。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-118">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="0c8ec-119">绑定</span><span class="sxs-lookup"><span data-stu-id="0c8ec-119">binding</span></span>|<span data-ttu-id="0c8ec-120">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-120">Optional string.</span></span> <span data-ttu-id="0c8ec-121">系统提供的一个绑定。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-121">One of the system-provided bindings.</span></span> <span data-ttu-id="0c8ec-122">有关列表，请参阅[System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-122">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="0c8ec-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0c8ec-123">bindingConfiguration</span></span>|<span data-ttu-id="0c8ec-124">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-124">Optional string.</span></span> <span data-ttu-id="0c8ec-125">指定在配置文件中找到的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-125">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c8ec-126">子元素</span><span class="sxs-lookup"><span data-stu-id="0c8ec-126">Child Elements</span></span>  
  
|<span data-ttu-id="0c8ec-127">元素</span><span class="sxs-lookup"><span data-stu-id="0c8ec-127">Element</span></span>|<span data-ttu-id="0c8ec-128">描述</span><span class="sxs-lookup"><span data-stu-id="0c8ec-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c8ec-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="0c8ec-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="0c8ec-130">指定此本地颁发者的标识信息。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-130">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="0c8ec-131">\<headers></span><span class="sxs-lookup"><span data-stu-id="0c8ec-131">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="0c8ec-132">地址头的集合，要正确书写本地颁发者的地址必须使用这些地址头。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-132">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="0c8ec-133">可以使用 `add` 关键字向此集合添加标头。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-133">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c8ec-134">父元素</span><span class="sxs-lookup"><span data-stu-id="0c8ec-134">Parent Elements</span></span>  
  
|<span data-ttu-id="0c8ec-135">元素</span><span class="sxs-lookup"><span data-stu-id="0c8ec-135">Element</span></span>|<span data-ttu-id="0c8ec-136">描述</span><span class="sxs-lookup"><span data-stu-id="0c8ec-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c8ec-137">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="0c8ec-137">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="0c8ec-138">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-138">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c8ec-139">备注</span><span class="sxs-lookup"><span data-stu-id="0c8ec-139">Remarks</span></span>  
 <span data-ttu-id="0c8ec-140">从安全令牌服务 (STS) 获取已颁发的令牌时，必须使用地址和绑定配置客户端应用程序，以将其用于与 STS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-140">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="0c8ec-141">当<xref:System.ServiceModel.WSFederationHttpBinding>不提供安全令牌服务，或者当联合绑定的颁发者地址的 URL`http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`或`null`，客户端的 Windows Communication Foundation (WCF) 通道使用指定的值来`address`和`binding`与 STS 以获取已颁发的令牌进行通信。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-141">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="0c8ec-142">有关配置本地颁发者的详细信息，请参阅[如何：配置本地颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-142">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c8ec-143">示例</span><span class="sxs-lookup"><span data-stu-id="0c8ec-143">Example</span></span>  
 <span data-ttu-id="0c8ec-144">下面的示例设置 `address` 元素的 `binding`、`bindingConfiguration` 和 `localIssuer` 属性。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-144">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c8ec-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c8ec-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="0c8ec-146">安全行为</span><span class="sxs-lookup"><span data-stu-id="0c8ec-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0c8ec-147">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="0c8ec-147">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="0c8ec-148">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="0c8ec-148">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0c8ec-149">安全行为</span><span class="sxs-lookup"><span data-stu-id="0c8ec-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0c8ec-150">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="0c8ec-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0c8ec-151">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="0c8ec-151">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0c8ec-152">保护客户端</span><span class="sxs-lookup"><span data-stu-id="0c8ec-152">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="0c8ec-153">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="0c8ec-153">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0c8ec-154">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="0c8ec-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
