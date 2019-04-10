---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 6bdf56e3d2084dec8d44e1c4d3f0c1e50b711b92
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153135"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="dc422-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="dc422-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="dc422-102">指定在联合安全方案中颁发的安全令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="dc422-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="dc422-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dc422-103">\<system.serviceModel></span></span>  
<span data-ttu-id="dc422-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="dc422-104">\<bindings></span></span>  
<span data-ttu-id="dc422-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="dc422-105">\<customBinding></span></span>  
<span data-ttu-id="dc422-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="dc422-106">\<binding></span></span>  
<span data-ttu-id="dc422-107">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="dc422-107">\<security></span></span>  
<span data-ttu-id="dc422-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="dc422-108">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc422-109">语法</span><span class="sxs-lookup"><span data-stu-id="dc422-109">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="dc422-110">类型</span><span class="sxs-lookup"><span data-stu-id="dc422-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc422-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dc422-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dc422-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dc422-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc422-113">特性</span><span class="sxs-lookup"><span data-stu-id="dc422-113">Attributes</span></span>  
  
|<span data-ttu-id="dc422-114">特性</span><span class="sxs-lookup"><span data-stu-id="dc422-114">Attribute</span></span>|<span data-ttu-id="dc422-115">描述</span><span class="sxs-lookup"><span data-stu-id="dc422-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc422-116">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="dc422-116">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="dc422-117">指定安全规范（WS-Security、WS-Trust、WS-Secure Conversation 和 WS-Security Policy）的版本，绑定必须支持这些安全规范。</span><span class="sxs-lookup"><span data-stu-id="dc422-117">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="dc422-118">此值的类型为 <xref:System.ServiceModel.MessageSecurityVersion>。</span><span class="sxs-lookup"><span data-stu-id="dc422-118">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="dc422-119">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="dc422-119">inclusionMode</span></span>|<span data-ttu-id="dc422-120">指定令牌包含要求。</span><span class="sxs-lookup"><span data-stu-id="dc422-120">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="dc422-121">此属性的类型为 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>。</span><span class="sxs-lookup"><span data-stu-id="dc422-121">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="dc422-122">keySize</span><span class="sxs-lookup"><span data-stu-id="dc422-122">keySize</span></span>|<span data-ttu-id="dc422-123">一个指定令牌的密钥大小的整数。</span><span class="sxs-lookup"><span data-stu-id="dc422-123">An integer that specifies the token key size.</span></span> <span data-ttu-id="dc422-124">默认值为 256。</span><span class="sxs-lookup"><span data-stu-id="dc422-124">The default value is 256.</span></span>|  
|<span data-ttu-id="dc422-125">keyType</span><span class="sxs-lookup"><span data-stu-id="dc422-125">keyType</span></span>|<span data-ttu-id="dc422-126">一个指定密钥类型的 <xref:System.IdentityModel.Tokens.SecurityKeyType> 的有效值。</span><span class="sxs-lookup"><span data-stu-id="dc422-126">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="dc422-127">默认值为 `SymmetricKey`。</span><span class="sxs-lookup"><span data-stu-id="dc422-127">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="dc422-128">tokenType</span><span class="sxs-lookup"><span data-stu-id="dc422-128">tokenType</span></span>|<span data-ttu-id="dc422-129">一个指定令牌类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="dc422-129">A string that specifies the token type.</span></span> <span data-ttu-id="dc422-130">默认值为“http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML”。</span><span class="sxs-lookup"><span data-stu-id="dc422-130">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc422-131">子元素</span><span class="sxs-lookup"><span data-stu-id="dc422-131">Child Elements</span></span>  
  
|<span data-ttu-id="dc422-132">元素</span><span class="sxs-lookup"><span data-stu-id="dc422-132">Element</span></span>|<span data-ttu-id="dc422-133">描述</span><span class="sxs-lookup"><span data-stu-id="dc422-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc422-134">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="dc422-134">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="dc422-135">一个用于指定附加请求参数的配置元素的集合。</span><span class="sxs-lookup"><span data-stu-id="dc422-135">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="dc422-136">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="dc422-136">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="dc422-137">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="dc422-137">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="dc422-138">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="dc422-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="dc422-139">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="dc422-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="dc422-140">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="dc422-140">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="dc422-141">\<issuer></span><span class="sxs-lookup"><span data-stu-id="dc422-141">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="dc422-142">一个用于指定颁发当前令牌的终结点的配置元素。</span><span class="sxs-lookup"><span data-stu-id="dc422-142">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="dc422-143">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="dc422-143">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="dc422-144">一个用于指定令牌颁发者的元数据的终结点地址的配置元素。</span><span class="sxs-lookup"><span data-stu-id="dc422-144">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc422-145">父元素</span><span class="sxs-lookup"><span data-stu-id="dc422-145">Parent Elements</span></span>  
  
|<span data-ttu-id="dc422-146">元素</span><span class="sxs-lookup"><span data-stu-id="dc422-146">Element</span></span>|<span data-ttu-id="dc422-147">描述</span><span class="sxs-lookup"><span data-stu-id="dc422-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc422-148">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="dc422-148">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="dc422-149">指定用于启动安全对话服务的默认值。</span><span class="sxs-lookup"><span data-stu-id="dc422-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="dc422-150">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="dc422-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="dc422-151">指定自定义绑定的安全选项。</span><span class="sxs-lookup"><span data-stu-id="dc422-151">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc422-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc422-152">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="dc422-153">绑定</span><span class="sxs-lookup"><span data-stu-id="dc422-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="dc422-154">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="dc422-154">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="dc422-155">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="dc422-155">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="dc422-156">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="dc422-156">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="dc422-157">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="dc422-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="dc422-158">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="dc422-158">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="dc422-159">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="dc422-159">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="dc422-160">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="dc422-160">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="dc422-161">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="dc422-161">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="dc422-162">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="dc422-162">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
