---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 055b7b49d1f775d49ac20de18c18ca0433716a23
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397863"
---
# <a name="localissuer"></a><span data-ttu-id="8ffa2-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="8ffa2-101">\<localIssuer></span></span>
<span data-ttu-id="8ffa2-102">指定要用于颁发安全令牌的本地颁发者的地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
<span data-ttu-id="8ffa2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8ffa2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8ffa2-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8ffa2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8ffa2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8ffa2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="8ffa2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8ffa2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="8ffa2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8ffa2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="8ffa2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="8ffa2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="8ffa2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="8ffa2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="8ffa2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<localIssuer >**</span><span class="sxs-lookup"><span data-stu-id="8ffa2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ffa2-111">语法</span><span class="sxs-lookup"><span data-stu-id="8ffa2-111">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ffa2-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8ffa2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8ffa2-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ffa2-114">特性</span><span class="sxs-lookup"><span data-stu-id="8ffa2-114">Attributes</span></span>  
  
|<span data-ttu-id="8ffa2-115">特性</span><span class="sxs-lookup"><span data-stu-id="8ffa2-115">Attribute</span></span>|<span data-ttu-id="8ffa2-116">描述</span><span class="sxs-lookup"><span data-stu-id="8ffa2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ffa2-117">地址</span><span class="sxs-lookup"><span data-stu-id="8ffa2-117">address</span></span>|<span data-ttu-id="8ffa2-118">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-118">Required string.</span></span> <span data-ttu-id="8ffa2-119">指定本地颁发者的 URI。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="8ffa2-120">绑定</span><span class="sxs-lookup"><span data-stu-id="8ffa2-120">binding</span></span>|<span data-ttu-id="8ffa2-121">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-121">Optional string.</span></span> <span data-ttu-id="8ffa2-122">系统提供的一个绑定。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-122">One of the system-provided bindings.</span></span> <span data-ttu-id="8ffa2-123">有关列表，请参阅[系统提供的绑定](../../../wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-123">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="8ffa2-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ffa2-124">bindingConfiguration</span></span>|<span data-ttu-id="8ffa2-125">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-125">Optional string.</span></span> <span data-ttu-id="8ffa2-126">指定在配置文件中找到的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ffa2-127">子元素</span><span class="sxs-lookup"><span data-stu-id="8ffa2-127">Child Elements</span></span>  
  
|<span data-ttu-id="8ffa2-128">元素</span><span class="sxs-lookup"><span data-stu-id="8ffa2-128">Element</span></span>|<span data-ttu-id="8ffa2-129">描述</span><span class="sxs-lookup"><span data-stu-id="8ffa2-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ffa2-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="8ffa2-130">\<identity></span></span>](identity.md)|<span data-ttu-id="8ffa2-131">指定此本地颁发者的标识信息。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="8ffa2-132">\<headers></span><span class="sxs-lookup"><span data-stu-id="8ffa2-132">\<headers></span></span>](headers-element.md)|<span data-ttu-id="8ffa2-133">地址头的集合，要正确书写本地颁发者的地址必须使用这些地址头。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="8ffa2-134">可以使用 `add` 关键字向此集合添加标头。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ffa2-135">父元素</span><span class="sxs-lookup"><span data-stu-id="8ffa2-135">Parent Elements</span></span>  
  
|<span data-ttu-id="8ffa2-136">元素</span><span class="sxs-lookup"><span data-stu-id="8ffa2-136">Element</span></span>|<span data-ttu-id="8ffa2-137">描述</span><span class="sxs-lookup"><span data-stu-id="8ffa2-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ffa2-138">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="8ffa2-138">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="8ffa2-139">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ffa2-140">备注</span><span class="sxs-lookup"><span data-stu-id="8ffa2-140">Remarks</span></span>  
 <span data-ttu-id="8ffa2-141">从安全令牌服务 (STS) 获取已颁发的令牌时，必须使用地址和绑定配置客户端应用程序，以将其用于与 STS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="8ffa2-142">如果未提供 security token service 的 URL，或者联合绑定的颁发者地址为`http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`或`null`时，则客户端的 Windows Communication Foundation （WCF）通道使用指定的值<xref:System.ServiceModel.WSFederationHttpBinding> `address`和`binding`与 STS 通信以获取颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="8ffa2-143">有关配置本地颁发者的详细信息，请[参阅如何：配置本地颁发者](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ffa2-144">示例</span><span class="sxs-lookup"><span data-stu-id="8ffa2-144">Example</span></span>  
 <span data-ttu-id="8ffa2-145">下面的示例设置 `address` 元素的 `binding`、`bindingConfiguration` 和 `localIssuer` 属性。</span><span class="sxs-lookup"><span data-stu-id="8ffa2-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8ffa2-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ffa2-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="8ffa2-147">安全行为</span><span class="sxs-lookup"><span data-stu-id="8ffa2-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8ffa2-148">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="8ffa2-148">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="8ffa2-149">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="8ffa2-149">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8ffa2-150">安全行为</span><span class="sxs-lookup"><span data-stu-id="8ffa2-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8ffa2-151">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="8ffa2-151">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8ffa2-152">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="8ffa2-152">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8ffa2-153">保护客户端</span><span class="sxs-lookup"><span data-stu-id="8ffa2-153">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="8ffa2-154">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="8ffa2-154">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="8ffa2-155">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="8ffa2-155">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
