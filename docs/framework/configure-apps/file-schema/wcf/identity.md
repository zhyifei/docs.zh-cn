---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 0f5eace346fd0ed2c0532fb602585c4593d97291
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220352"
---
# <a name="identity"></a><span data-ttu-id="caf9d-101">\<identity></span><span class="sxs-lookup"><span data-stu-id="caf9d-101">\<identity></span></span>
<span data-ttu-id="caf9d-102">标识元素允许客户端开发人员在设计时指定服务的期望标识。</span><span class="sxs-lookup"><span data-stu-id="caf9d-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="caf9d-103">在客户端和服务之间的握手过程中，Windows Communication Foundation (WCF) 基础结构将确保预期的服务匹配此元素的值的标识，因此可以进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="caf9d-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="caf9d-104">有关详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="caf9d-104">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="caf9d-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="caf9d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="caf9d-106">\<client></span><span class="sxs-lookup"><span data-stu-id="caf9d-106">\<client></span></span>  
<span data-ttu-id="caf9d-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="caf9d-107">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caf9d-108">语法</span><span class="sxs-lookup"><span data-stu-id="caf9d-108">Syntax</span></span>  
  
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
  <usePrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="caf9d-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="caf9d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="caf9d-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="caf9d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="caf9d-111">特性</span><span class="sxs-lookup"><span data-stu-id="caf9d-111">Attributes</span></span>  
 <span data-ttu-id="caf9d-112">无。</span><span class="sxs-lookup"><span data-stu-id="caf9d-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="caf9d-113">子元素</span><span class="sxs-lookup"><span data-stu-id="caf9d-113">Child Elements</span></span>  
  
|<span data-ttu-id="caf9d-114">元素</span><span class="sxs-lookup"><span data-stu-id="caf9d-114">Element</span></span>|<span data-ttu-id="caf9d-115">描述</span><span class="sxs-lookup"><span data-stu-id="caf9d-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="caf9d-116">证书</span><span class="sxs-lookup"><span data-stu-id="caf9d-116">certificate</span></span>|<span data-ttu-id="caf9d-117">指定 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="caf9d-117">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="caf9d-118">此元素的类型为 <xref:System.ServiceModel.Configuration.CertificateElement>。</span><span class="sxs-lookup"><span data-stu-id="caf9d-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="caf9d-119">它包含一个 `encodedValue` 属性，该属性是一个字符串，用于指定此证书编码的值。</span><span class="sxs-lookup"><span data-stu-id="caf9d-119">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="caf9d-120">certificateReference</span><span class="sxs-lookup"><span data-stu-id="caf9d-120">certificateReference</span></span>|<span data-ttu-id="caf9d-121">指定 X.509 证书验证的设置。</span><span class="sxs-lookup"><span data-stu-id="caf9d-121">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="caf9d-122">此元素的类型为 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>。</span><span class="sxs-lookup"><span data-stu-id="caf9d-122">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="caf9d-123">dns</span><span class="sxs-lookup"><span data-stu-id="caf9d-123">dns</span></span>|<span data-ttu-id="caf9d-124">指定用于对服务进行身份验证的 X.509 证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="caf9d-124">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="caf9d-125">此元素包含一个字符串属性 `value`，并包含实际的标识。</span><span class="sxs-lookup"><span data-stu-id="caf9d-125">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="caf9d-126">rsa</span><span class="sxs-lookup"><span data-stu-id="caf9d-126">rsa</span></span>|<span data-ttu-id="caf9d-127">指定用于向客户端验证服务身份的 X.509 证书的 RSA 字段的值。</span><span class="sxs-lookup"><span data-stu-id="caf9d-127">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="caf9d-128">此元素包含一个字符串属性 `value`，并包含实际的标识。</span><span class="sxs-lookup"><span data-stu-id="caf9d-128">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="caf9d-129">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="caf9d-129">servicePrincipalName</span></span>|<span data-ttu-id="caf9d-130">指定服务器主体名称 (SPN) 标识，它是客户端用来唯一标识一个服务实例的主体名称。</span><span class="sxs-lookup"><span data-stu-id="caf9d-130">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="caf9d-131">此元素包含一个 `value` 属性，该属性是一个字符串，其中包含实际的主体名称。</span><span class="sxs-lookup"><span data-stu-id="caf9d-131">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="caf9d-132">此元素的类型为 <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>。</span><span class="sxs-lookup"><span data-stu-id="caf9d-132">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="caf9d-133">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="caf9d-133">userPrincipalName</span></span>|<span data-ttu-id="caf9d-134">指定用户主体名称 (UPN) 标识，它是网络上的用户登录名类型。</span><span class="sxs-lookup"><span data-stu-id="caf9d-134">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="caf9d-135">用户主体名称包含用户对象名称后跟的 Active Directory 中使用 at 符号 (\@)，然后，通常情况下，域名系统父域。</span><span class="sxs-lookup"><span data-stu-id="caf9d-135">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="caf9d-136">例如，Fabrikam.com 域树中的 Jeff 可能具有用户主体名称[ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com)。</span><span class="sxs-lookup"><span data-stu-id="caf9d-136">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="caf9d-137">此元素包含一个 `value` 属性，该属性是一个字符串，其中包含实际的主体名称。</span><span class="sxs-lookup"><span data-stu-id="caf9d-137">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="caf9d-138">此元素的类型为 <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>。</span><span class="sxs-lookup"><span data-stu-id="caf9d-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="caf9d-139">父元素</span><span class="sxs-lookup"><span data-stu-id="caf9d-139">Parent Elements</span></span>  
  
|<span data-ttu-id="caf9d-140">元素</span><span class="sxs-lookup"><span data-stu-id="caf9d-140">Element</span></span>|<span data-ttu-id="caf9d-141">描述</span><span class="sxs-lookup"><span data-stu-id="caf9d-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="caf9d-142">\<custom></span><span class="sxs-lookup"><span data-stu-id="caf9d-142">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="caf9d-143">指定 netPeerTcpBinding 的自定义对等解析程序。</span><span class="sxs-lookup"><span data-stu-id="caf9d-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="caf9d-144">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="caf9d-144">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="caf9d-145">配置服务终结点。</span><span class="sxs-lookup"><span data-stu-id="caf9d-145">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="caf9d-146">\<终结点 > 的\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="caf9d-146">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="caf9d-147">配置通道终结点。</span><span class="sxs-lookup"><span data-stu-id="caf9d-147">Configures channel endpoints.</span></span>|  
|[<span data-ttu-id="caf9d-148">\<issuer></span><span class="sxs-lookup"><span data-stu-id="caf9d-148">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="caf9d-149">指定联合服务的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="caf9d-149">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="caf9d-150">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="caf9d-150">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="caf9d-151">指定联合服务的安全令牌服务 (STS) 的元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="caf9d-151">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="caf9d-152">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="caf9d-152">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="caf9d-153">定义自定义绑定中的已颁发令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="caf9d-153">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="caf9d-154">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="caf9d-154">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="caf9d-155">指定本地安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="caf9d-155">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="caf9d-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="caf9d-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="caf9d-157">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="caf9d-157">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="caf9d-158">终结点：地址、 绑定和协定</span><span class="sxs-lookup"><span data-stu-id="caf9d-158">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
