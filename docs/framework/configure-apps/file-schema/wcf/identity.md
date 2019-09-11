---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 15c9e38a141fc294c47863b1a932711444ac079a
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855150"
---
# <a name="identity"></a><span data-ttu-id="ec559-101">\<身份 ></span><span class="sxs-lookup"><span data-stu-id="ec559-101">\<identity></span></span>
<span data-ttu-id="ec559-102">标识元素允许客户端开发人员在设计时指定服务的期望标识。</span><span class="sxs-lookup"><span data-stu-id="ec559-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="ec559-103">在客户端与服务之间的握手过程中，Windows Communication Foundation （WCF）基础结构将确保预期服务的标识与此元素的值相匹配，因而可以进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ec559-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="ec559-104">有关详细信息，请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="ec559-104">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="ec559-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ec559-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ec559-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ec559-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ec559-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="ec559-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="ec559-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<终结点 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="ec559-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="ec559-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<身份 >**</span><span class="sxs-lookup"><span data-stu-id="ec559-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec559-110">语法</span><span class="sxs-lookup"><span data-stu-id="ec559-110">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec559-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ec559-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ec559-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ec559-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec559-113">特性</span><span class="sxs-lookup"><span data-stu-id="ec559-113">Attributes</span></span>  
 <span data-ttu-id="ec559-114">无。</span><span class="sxs-lookup"><span data-stu-id="ec559-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec559-115">子元素</span><span class="sxs-lookup"><span data-stu-id="ec559-115">Child Elements</span></span>  
  
|<span data-ttu-id="ec559-116">元素</span><span class="sxs-lookup"><span data-stu-id="ec559-116">Element</span></span>|<span data-ttu-id="ec559-117">描述</span><span class="sxs-lookup"><span data-stu-id="ec559-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec559-118">证书 (certificate)</span><span class="sxs-lookup"><span data-stu-id="ec559-118">certificate</span></span>|<span data-ttu-id="ec559-119">指定 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="ec559-119">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="ec559-120">此元素的类型为 <xref:System.ServiceModel.Configuration.CertificateElement>。</span><span class="sxs-lookup"><span data-stu-id="ec559-120">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="ec559-121">它包含一个 `encodedValue` 属性，该属性是一个字符串，用于指定此证书编码的值。</span><span class="sxs-lookup"><span data-stu-id="ec559-121">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="ec559-122">certificateReference</span><span class="sxs-lookup"><span data-stu-id="ec559-122">certificateReference</span></span>|<span data-ttu-id="ec559-123">指定 X.509 证书验证的设置。</span><span class="sxs-lookup"><span data-stu-id="ec559-123">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="ec559-124">此元素的类型为 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>。</span><span class="sxs-lookup"><span data-stu-id="ec559-124">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="ec559-125">dns</span><span class="sxs-lookup"><span data-stu-id="ec559-125">dns</span></span>|<span data-ttu-id="ec559-126">指定用于对服务进行身份验证的 X.509 证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="ec559-126">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="ec559-127">此元素包含一个字符串属性 `value`，并包含实际的标识。</span><span class="sxs-lookup"><span data-stu-id="ec559-127">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="ec559-128">rsa</span><span class="sxs-lookup"><span data-stu-id="ec559-128">rsa</span></span>|<span data-ttu-id="ec559-129">指定用于向客户端验证服务身份的 X.509 证书的 RSA 字段的值。</span><span class="sxs-lookup"><span data-stu-id="ec559-129">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="ec559-130">此元素包含一个字符串属性 `value`，并包含实际的标识。</span><span class="sxs-lookup"><span data-stu-id="ec559-130">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="ec559-131">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="ec559-131">servicePrincipalName</span></span>|<span data-ttu-id="ec559-132">指定服务器主体名称 (SPN) 标识，它是客户端用来唯一标识一个服务实例的主体名称。</span><span class="sxs-lookup"><span data-stu-id="ec559-132">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="ec559-133">此元素包含一个 `value` 属性，该属性是一个字符串，其中包含实际的主体名称。</span><span class="sxs-lookup"><span data-stu-id="ec559-133">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="ec559-134">此元素的类型为 <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>。</span><span class="sxs-lookup"><span data-stu-id="ec559-134">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="ec559-135">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="ec559-135">userPrincipalName</span></span>|<span data-ttu-id="ec559-136">指定用户主体名称 (UPN) 标识，它是网络上的用户登录名类型。</span><span class="sxs-lookup"><span data-stu-id="ec559-136">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="ec559-137">用户主体名称包含 Active Directory 中使用的用户对象名称，后跟 at 符号（\@），然后通常是域名系统的父域。</span><span class="sxs-lookup"><span data-stu-id="ec559-137">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="ec559-138">例如，Fabrikam.com 域树中的 Jeff 可能具有用户主体名称[jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com)。</span><span class="sxs-lookup"><span data-stu-id="ec559-138">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="ec559-139">此元素包含一个 `value` 属性，该属性是一个字符串，其中包含实际的主体名称。</span><span class="sxs-lookup"><span data-stu-id="ec559-139">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="ec559-140">此元素的类型为 <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>。</span><span class="sxs-lookup"><span data-stu-id="ec559-140">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec559-141">父元素</span><span class="sxs-lookup"><span data-stu-id="ec559-141">Parent Elements</span></span>  
  
|<span data-ttu-id="ec559-142">元素</span><span class="sxs-lookup"><span data-stu-id="ec559-142">Element</span></span>|<span data-ttu-id="ec559-143">描述</span><span class="sxs-lookup"><span data-stu-id="ec559-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec559-144">\<custom></span><span class="sxs-lookup"><span data-stu-id="ec559-144">\<custom></span></span>](custom.md)|<span data-ttu-id="ec559-145">指定 netPeerTcpBinding 的自定义对等解析程序。</span><span class="sxs-lookup"><span data-stu-id="ec559-145">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="ec559-146">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="ec559-146">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="ec559-147">配置服务终结点。</span><span class="sxs-lookup"><span data-stu-id="ec559-147">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="ec559-148">\<\<客户端 > > 终结点</span><span class="sxs-lookup"><span data-stu-id="ec559-148">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="ec559-149">配置通道终结点。</span><span class="sxs-lookup"><span data-stu-id="ec559-149">Configures channel endpoints.</span></span>|  
|[<span data-ttu-id="ec559-150">\<issuer></span><span class="sxs-lookup"><span data-stu-id="ec559-150">\<issuer></span></span>](issuer.md)|<span data-ttu-id="ec559-151">指定联合服务的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="ec559-151">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="ec559-152">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="ec559-152">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="ec559-153">指定联合服务的安全令牌服务 (STS) 的元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="ec559-153">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="ec559-154">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="ec559-154">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="ec559-155">定义自定义绑定中的已颁发令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="ec559-155">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="ec559-156">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="ec559-156">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="ec559-157">指定本地安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="ec559-157">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec559-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec559-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="ec559-159">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="ec559-159">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ec559-160">终结点地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="ec559-160">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
