---
title: '&lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 2060f98e94cec9e656420ac073204a82bc592b92
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149236"
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="6e30b-102">&lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="6e30b-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="6e30b-103">指定在联合安全方案中颁发的安全令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="6e30b-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="6e30b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6e30b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6e30b-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6e30b-105">\<bindings></span></span>  
<span data-ttu-id="6e30b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6e30b-106">\<customBinding></span></span>  
<span data-ttu-id="6e30b-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6e30b-107">\<binding></span></span>  
<span data-ttu-id="6e30b-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="6e30b-108">\<security></span></span>  
<span data-ttu-id="6e30b-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="6e30b-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e30b-110">语法</span><span class="sxs-lookup"><span data-stu-id="6e30b-110">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="6e30b-111">类型</span><span class="sxs-lookup"><span data-stu-id="6e30b-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e30b-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6e30b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6e30b-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6e30b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e30b-114">特性</span><span class="sxs-lookup"><span data-stu-id="6e30b-114">Attributes</span></span>  
  
|<span data-ttu-id="6e30b-115">特性</span><span class="sxs-lookup"><span data-stu-id="6e30b-115">Attribute</span></span>|<span data-ttu-id="6e30b-116">描述</span><span class="sxs-lookup"><span data-stu-id="6e30b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e30b-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="6e30b-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="6e30b-118">指定安全规范（WS-Security、WS-Trust、WS-Secure Conversation 和 WS-Security Policy）的版本，绑定必须支持这些安全规范。</span><span class="sxs-lookup"><span data-stu-id="6e30b-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="6e30b-119">此值的类型为 <xref:System.ServiceModel.MessageSecurityVersion>。</span><span class="sxs-lookup"><span data-stu-id="6e30b-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="6e30b-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="6e30b-120">inclusionMode</span></span>|<span data-ttu-id="6e30b-121">指定令牌包含要求。</span><span class="sxs-lookup"><span data-stu-id="6e30b-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="6e30b-122">此属性的类型为 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>。</span><span class="sxs-lookup"><span data-stu-id="6e30b-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="6e30b-123">keySize</span><span class="sxs-lookup"><span data-stu-id="6e30b-123">keySize</span></span>|<span data-ttu-id="6e30b-124">一个指定令牌的密钥大小的整数。</span><span class="sxs-lookup"><span data-stu-id="6e30b-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="6e30b-125">默认值为 256。</span><span class="sxs-lookup"><span data-stu-id="6e30b-125">The default value is 256.</span></span>|  
|<span data-ttu-id="6e30b-126">keyType</span><span class="sxs-lookup"><span data-stu-id="6e30b-126">keyType</span></span>|<span data-ttu-id="6e30b-127">一个指定密钥类型的 <xref:System.IdentityModel.Tokens.SecurityKeyType> 的有效值。</span><span class="sxs-lookup"><span data-stu-id="6e30b-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="6e30b-128">默认值为 `SymmetricKey`。</span><span class="sxs-lookup"><span data-stu-id="6e30b-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="6e30b-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="6e30b-129">tokenType</span></span>|<span data-ttu-id="6e30b-130">一个指定令牌类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="6e30b-130">A string that specifies the token type.</span></span> <span data-ttu-id="6e30b-131">默认值为“http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML”。</span><span class="sxs-lookup"><span data-stu-id="6e30b-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e30b-132">子元素</span><span class="sxs-lookup"><span data-stu-id="6e30b-132">Child Elements</span></span>  
  
|<span data-ttu-id="6e30b-133">元素</span><span class="sxs-lookup"><span data-stu-id="6e30b-133">Element</span></span>|<span data-ttu-id="6e30b-134">描述</span><span class="sxs-lookup"><span data-stu-id="6e30b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e30b-135">\<additionalRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="6e30b-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="6e30b-136">一个用于指定附加请求参数的配置元素的集合。</span><span class="sxs-lookup"><span data-stu-id="6e30b-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="6e30b-137">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="6e30b-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="6e30b-138">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="6e30b-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="6e30b-139">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="6e30b-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="6e30b-140">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="6e30b-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="6e30b-141">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="6e30b-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="6e30b-142">\<issuer></span><span class="sxs-lookup"><span data-stu-id="6e30b-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="6e30b-143">一个用于指定颁发当前令牌的终结点的配置元素。</span><span class="sxs-lookup"><span data-stu-id="6e30b-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="6e30b-144">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="6e30b-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="6e30b-145">一个用于指定令牌颁发者的元数据的终结点地址的配置元素。</span><span class="sxs-lookup"><span data-stu-id="6e30b-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e30b-146">父元素</span><span class="sxs-lookup"><span data-stu-id="6e30b-146">Parent Elements</span></span>  
  
|<span data-ttu-id="6e30b-147">元素</span><span class="sxs-lookup"><span data-stu-id="6e30b-147">Element</span></span>|<span data-ttu-id="6e30b-148">描述</span><span class="sxs-lookup"><span data-stu-id="6e30b-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e30b-149">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="6e30b-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="6e30b-150">指定用于启动安全对话服务的默认值。</span><span class="sxs-lookup"><span data-stu-id="6e30b-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="6e30b-151">\<security></span><span class="sxs-lookup"><span data-stu-id="6e30b-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="6e30b-152">指定自定义绑定的安全选项。</span><span class="sxs-lookup"><span data-stu-id="6e30b-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e30b-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e30b-153">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="6e30b-154">绑定</span><span class="sxs-lookup"><span data-stu-id="6e30b-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6e30b-155">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="6e30b-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="6e30b-156">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="6e30b-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="6e30b-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6e30b-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="6e30b-158">如何：创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="6e30b-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="6e30b-159">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="6e30b-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)  
 [<span data-ttu-id="6e30b-160">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="6e30b-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="6e30b-161">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="6e30b-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="6e30b-162">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="6e30b-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="6e30b-163">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="6e30b-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
