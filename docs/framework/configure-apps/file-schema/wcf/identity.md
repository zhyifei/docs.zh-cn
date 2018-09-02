---
title: '&lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: c77f60badd80973f0eeb36f6195b1d4b7617c386
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404265"
---
# <a name="ltidentitygt"></a><span data-ttu-id="a8993-102">&lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="a8993-102">&lt;identity&gt;</span></span>
<span data-ttu-id="a8993-103">标识元素允许客户端开发人员在设计时指定服务的期望标识。</span><span class="sxs-lookup"><span data-stu-id="a8993-103">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="a8993-104">在客户端和服务之间的握手过程中，Windows Communication Foundation (WCF) 基础结构将确保预期的服务匹配此元素的值的标识，因此可以进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a8993-104">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="a8993-105">有关详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="a8993-105">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="a8993-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a8993-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="a8993-107">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="a8993-107">\<client></span></span>  
<span data-ttu-id="a8993-108">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="a8993-108">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8993-109">语法</span><span class="sxs-lookup"><span data-stu-id="a8993-109">Syntax</span></span>  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8993-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a8993-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a8993-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a8993-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8993-112">特性</span><span class="sxs-lookup"><span data-stu-id="a8993-112">Attributes</span></span>  
 <span data-ttu-id="a8993-113">无。</span><span class="sxs-lookup"><span data-stu-id="a8993-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8993-114">子元素</span><span class="sxs-lookup"><span data-stu-id="a8993-114">Child Elements</span></span>  
  
|<span data-ttu-id="a8993-115">元素</span><span class="sxs-lookup"><span data-stu-id="a8993-115">Element</span></span>|<span data-ttu-id="a8993-116">描述</span><span class="sxs-lookup"><span data-stu-id="a8993-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8993-117">certificate</span><span class="sxs-lookup"><span data-stu-id="a8993-117">certificate</span></span>|<span data-ttu-id="a8993-118">指定 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="a8993-118">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="a8993-119">此元素的类型为 <xref:System.ServiceModel.Configuration.CertificateElement>。</span><span class="sxs-lookup"><span data-stu-id="a8993-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="a8993-120">它包含一个 `encodedValue` 属性，该属性是一个字符串，用于指定此证书编码的值。</span><span class="sxs-lookup"><span data-stu-id="a8993-120">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="a8993-121">certificateReference</span><span class="sxs-lookup"><span data-stu-id="a8993-121">certificateReference</span></span>|<span data-ttu-id="a8993-122">指定 X.509 证书验证的设置。</span><span class="sxs-lookup"><span data-stu-id="a8993-122">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="a8993-123">此元素的类型为 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>。</span><span class="sxs-lookup"><span data-stu-id="a8993-123">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="a8993-124">dns</span><span class="sxs-lookup"><span data-stu-id="a8993-124">dns</span></span>|<span data-ttu-id="a8993-125">指定用于对服务进行身份验证的 X.509 证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="a8993-125">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="a8993-126">此元素包含一个字符串属性 `value`，并包含实际的标识。</span><span class="sxs-lookup"><span data-stu-id="a8993-126">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="a8993-127">rsa</span><span class="sxs-lookup"><span data-stu-id="a8993-127">rsa</span></span>|<span data-ttu-id="a8993-128">指定用于向客户端验证服务身份的 X.509 证书的 RSA 字段的值。</span><span class="sxs-lookup"><span data-stu-id="a8993-128">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="a8993-129">此元素包含一个字符串属性 `value`，并包含实际的标识。</span><span class="sxs-lookup"><span data-stu-id="a8993-129">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="a8993-130">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="a8993-130">servicePrincipalName</span></span>|<span data-ttu-id="a8993-131">指定服务器主体名称 (SPN) 标识，它是客户端用来唯一标识一个服务实例的主体名称。</span><span class="sxs-lookup"><span data-stu-id="a8993-131">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="a8993-132">此元素包含一个 `value` 属性，该属性是一个字符串，其中包含实际的主体名称。</span><span class="sxs-lookup"><span data-stu-id="a8993-132">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="a8993-133">此元素的类型为 <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>。</span><span class="sxs-lookup"><span data-stu-id="a8993-133">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="a8993-134">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a8993-134">userPrincipalName</span></span>|<span data-ttu-id="a8993-135">指定用户主体名称 (UPN) 标识，它是网络上的用户登录名类型。</span><span class="sxs-lookup"><span data-stu-id="a8993-135">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="a8993-136">用户主体名称包含用户对象名称后跟的 Active Directory 中使用 at 符号 (\@)，然后，通常情况下，域名系统父域。</span><span class="sxs-lookup"><span data-stu-id="a8993-136">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="a8993-137">例如，Fabrikam.com 域树中的 Jeff 可能具有用户主体名称[ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com)。</span><span class="sxs-lookup"><span data-stu-id="a8993-137">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="a8993-138">此元素包含一个 `value` 属性，该属性是一个字符串，其中包含实际的主体名称。</span><span class="sxs-lookup"><span data-stu-id="a8993-138">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="a8993-139">此元素的类型为 <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>。</span><span class="sxs-lookup"><span data-stu-id="a8993-139">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8993-140">父元素</span><span class="sxs-lookup"><span data-stu-id="a8993-140">Parent Elements</span></span>  
  
|<span data-ttu-id="a8993-141">元素</span><span class="sxs-lookup"><span data-stu-id="a8993-141">Element</span></span>|<span data-ttu-id="a8993-142">描述</span><span class="sxs-lookup"><span data-stu-id="a8993-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8993-143">\<custom></span><span class="sxs-lookup"><span data-stu-id="a8993-143">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="a8993-144">指定 netPeerTcpBinding 的自定义对等解析程序。</span><span class="sxs-lookup"><span data-stu-id="a8993-144">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="a8993-145">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="a8993-145">\<endpoint></span></span>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)|<span data-ttu-id="a8993-146">配置不同类型的终结点。</span><span class="sxs-lookup"><span data-stu-id="a8993-146">Configures different types of endpoints.</span></span>|  
|[<span data-ttu-id="a8993-147">\<issuer></span><span class="sxs-lookup"><span data-stu-id="a8993-147">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="a8993-148">指定联合服务的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="a8993-148">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="a8993-149">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="a8993-149">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="a8993-150">指定联合服务的安全令牌服务 (STS) 的元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="a8993-150">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="a8993-151">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="a8993-151">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="a8993-152">定义自定义绑定中的已颁发令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="a8993-152">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="a8993-153">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="a8993-153">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="a8993-154">指定本地安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="a8993-154">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8993-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8993-155">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [<span data-ttu-id="a8993-156">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="a8993-156">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a8993-157">终结点：地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="a8993-157">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
