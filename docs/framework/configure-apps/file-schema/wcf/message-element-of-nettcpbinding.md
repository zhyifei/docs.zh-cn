---
title: "&lt;netTcpBinding&gt; 的 &lt;message&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d71edd9-c085-4c2e-b6d3-980c313366f9
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6907db64b4e9de4c60ac2a97f09f294a0ee81e86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-element-of-ltnettcpbindinggt"></a><span data-ttu-id="9024d-102">&lt;netTcpBinding&gt; 的 &lt;message&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="9024d-102">&lt;message&gt; element of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="9024d-103">定义与配置的终结点的消息级安全性要求的类型[ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9024d-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="9024d-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9024d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9024d-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9024d-105">\<bindings></span></span>  
<span data-ttu-id="9024d-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="9024d-106">\<netTcpBinding></span></span>  
<span data-ttu-id="9024d-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9024d-107">\<binding></span></span>  
<span data-ttu-id="9024d-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="9024d-108">\<security></span></span>  
<span data-ttu-id="9024d-109">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="9024d-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9024d-110">语法</span><span class="sxs-lookup"><span data-stu-id="9024d-110">Syntax</span></span>  
  
```xml  
<message   
      algorithmSuite=System.Servicemodel.Security.SecurityAlgorithmsuite  
    clientCredentialType="None/Windows/UserName/Certificate/IssuedToken"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9024d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9024d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9024d-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9024d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9024d-113">特性</span><span class="sxs-lookup"><span data-stu-id="9024d-113">Attributes</span></span>  
  
|<span data-ttu-id="9024d-114">特性</span><span class="sxs-lookup"><span data-stu-id="9024d-114">Attribute</span></span>|<span data-ttu-id="9024d-115">描述</span><span class="sxs-lookup"><span data-stu-id="9024d-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="9024d-116">设置消息加密和密钥包装算法。</span><span class="sxs-lookup"><span data-stu-id="9024d-116">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="9024d-117">算法和密钥大小由 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 类确定。</span><span class="sxs-lookup"><span data-stu-id="9024d-117">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="9024d-118">这些算法映射到安全策略语言 (WS-SecurityPolicy) 规范中指定的算法。</span><span class="sxs-lookup"><span data-stu-id="9024d-118">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="9024d-119">下表列出了可能的值。</span><span class="sxs-lookup"><span data-stu-id="9024d-119">Possible values are shown in the following table.</span></span> <span data-ttu-id="9024d-120">默认值为 `Basic256`。</span><span class="sxs-lookup"><span data-stu-id="9024d-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="9024d-121">如果服务绑定指定的 `algorithmSuite` 值不等于默认值，并且您使用 Svcutil.exe 生成配置文件，则不会正确生成该文件，您必须手动编辑此配置文件，将此属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="9024d-121">If the service binding specifies an `algorithmSuite` value that is not equal to the default, and you generate the configuration file using Svcutil.exe, then it is not generated correctly, and you must manually edit the configuration file to set this attribute to the desired value.</span></span>|  
|`clientCredentialType`|<span data-ttu-id="9024d-122">指定要在使用基于消息的安全性执行客户端身份验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="9024d-122">Specifies the type of credential to be used when performing client authentication using Message-based security.</span></span> <span data-ttu-id="9024d-123">下表列出了可能的值。</span><span class="sxs-lookup"><span data-stu-id="9024d-123">Possible values are shown in the following table.</span></span> <span data-ttu-id="9024d-124">默认值为 `UserName`。</span><span class="sxs-lookup"><span data-stu-id="9024d-124">The default value is `UserName`.</span></span> <span data-ttu-id="9024d-125">此属性的类型为 <xref:System.ServiceModel.MessageCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="9024d-125">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="9024d-126">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="9024d-126">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="9024d-127">值</span><span class="sxs-lookup"><span data-stu-id="9024d-127">Value</span></span>|<span data-ttu-id="9024d-128">描述</span><span class="sxs-lookup"><span data-stu-id="9024d-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9024d-129">Basic128</span><span class="sxs-lookup"><span data-stu-id="9024d-129">Basic128</span></span>|<span data-ttu-id="9024d-130">使用 Aes128 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="9024d-130">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9024d-131">Basic192</span><span class="sxs-lookup"><span data-stu-id="9024d-131">Basic192</span></span>|<span data-ttu-id="9024d-132">使用 Aes192 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="9024d-132">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9024d-133">Basic256</span><span class="sxs-lookup"><span data-stu-id="9024d-133">Basic256</span></span>|<span data-ttu-id="9024d-134">使用 Aes256 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="9024d-134">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9024d-135">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9024d-135">Basic256Rsa15</span></span>|<span data-ttu-id="9024d-136">对消息加密使用 Aes256，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="9024d-136">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9024d-137">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="9024d-137">Basic192Rsa15</span></span>|<span data-ttu-id="9024d-138">对消息加密使用 Aes192，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="9024d-138">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9024d-139">TripleDes</span><span class="sxs-lookup"><span data-stu-id="9024d-139">TripleDes</span></span>|<span data-ttu-id="9024d-140">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="9024d-140">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9024d-141">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="9024d-141">Basic128Rsa15</span></span>|<span data-ttu-id="9024d-142">对消息加密使用 Aes128，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="9024d-142">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9024d-143">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="9024d-143">TripleDesRsa15</span></span>|<span data-ttu-id="9024d-144">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="9024d-144">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9024d-145">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="9024d-145">Basic128Sha256</span></span>|<span data-ttu-id="9024d-146">对消息加密使用 Aes256，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="9024d-146">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9024d-147">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="9024d-147">Basic192Sha256</span></span>|<span data-ttu-id="9024d-148">对消息加密使用 Aes192，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="9024d-148">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9024d-149">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="9024d-149">Basic256Sha256</span></span>|<span data-ttu-id="9024d-150">对消息加密使用 Aes256，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="9024d-150">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9024d-151">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="9024d-151">TripleDesSha256</span></span>|<span data-ttu-id="9024d-152">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="9024d-152">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9024d-153">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9024d-153">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="9024d-154">对消息加密使用 Aes128，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="9024d-154">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9024d-155">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9024d-155">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="9024d-156">对消息加密使用 Aes192，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="9024d-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9024d-157">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9024d-157">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="9024d-158">对消息加密使用 Aes256，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="9024d-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9024d-159">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9024d-159">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="9024d-160">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="9024d-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9024d-161">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="9024d-161">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9024d-162">值</span><span class="sxs-lookup"><span data-stu-id="9024d-162">Value</span></span>|<span data-ttu-id="9024d-163">描述</span><span class="sxs-lookup"><span data-stu-id="9024d-163">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9024d-164">无</span><span class="sxs-lookup"><span data-stu-id="9024d-164">None</span></span>|<span data-ttu-id="9024d-165">允许服务与匿名客户端交互。</span><span class="sxs-lookup"><span data-stu-id="9024d-165">This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="9024d-166">对于服务，这表示服务不需要任何客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="9024d-166">On the service, this indicates that the service does not require any client credential.</span></span> <span data-ttu-id="9024d-167">对于客户端，这表示客户端不提供任何客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="9024d-167">On the client, this indicates that the client does not provide any client credential.</span></span>|  
|<span data-ttu-id="9024d-168">Windows</span><span class="sxs-lookup"><span data-stu-id="9024d-168">Windows</span></span>|<span data-ttu-id="9024d-169">允许 SOAP 交换在已通过身份验证的 Windows 凭据上下文中执行。</span><span class="sxs-lookup"><span data-stu-id="9024d-169">Allows the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span>|  
|<span data-ttu-id="9024d-170">UserName</span><span class="sxs-lookup"><span data-stu-id="9024d-170">UserName</span></span>|<span data-ttu-id="9024d-171">允许服务要求使用 UserName 凭据对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9024d-171">Allows the service to require that the client be authenticated using a UserName credential.</span></span> [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="9024d-172"> 不支持发送密码摘要，也不支持使用密码派生密钥并使用这样的密钥来提供消息安全性。</span><span class="sxs-lookup"><span data-stu-id="9024d-172"> does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="9024d-173">因此，在使用 UserName 凭据时，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 将确保传输的安全性。</span><span class="sxs-lookup"><span data-stu-id="9024d-173">As such, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the transport is secured when using UserName credentials.</span></span> <span data-ttu-id="9024d-174">这种凭据模式将产生可互操作的交换或不可互操作的协商，具体取决于 `negotiateServiceCredential` 属性。</span><span class="sxs-lookup"><span data-stu-id="9024d-174">This credential mode results in either an interoperable exchange or a non-interoperable negotiation based on the `negotiateServiceCredential` attribute.</span></span>|  
|<span data-ttu-id="9024d-175">证书</span><span class="sxs-lookup"><span data-stu-id="9024d-175">Certificate</span></span>|<span data-ttu-id="9024d-176">允许服务要求使用证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9024d-176">Allows the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="9024d-177">如果使用消息安全模式并且将 `negotiateServiceCredential` 属性设置为 `false`，则必须向客户端提供服务证书。</span><span class="sxs-lookup"><span data-stu-id="9024d-177">If message security mode is used and the `negotiateServiceCredential` attribute is set to `false`, the client must be provisioned with the service certificate.</span></span>|  
|<span data-ttu-id="9024d-178">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="9024d-178">IssuedToken</span></span>|<span data-ttu-id="9024d-179">指定自定义令牌，该令牌通常由安全令牌服务 (STS) 颁发。</span><span class="sxs-lookup"><span data-stu-id="9024d-179">Specifies a custom token, usually issued by a Security Token Service (STS).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9024d-180">子元素</span><span class="sxs-lookup"><span data-stu-id="9024d-180">Child Elements</span></span>  
 <span data-ttu-id="9024d-181">无</span><span class="sxs-lookup"><span data-stu-id="9024d-181">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9024d-182">父元素</span><span class="sxs-lookup"><span data-stu-id="9024d-182">Parent Elements</span></span>  
  
|<span data-ttu-id="9024d-183">元素</span><span class="sxs-lookup"><span data-stu-id="9024d-183">Element</span></span>|<span data-ttu-id="9024d-184">描述</span><span class="sxs-lookup"><span data-stu-id="9024d-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9024d-185">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="9024d-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="9024d-186">定义 <xref:System.ServiceModel.Configuration.NetTcpBindingElement>的安全功能。</span><span class="sxs-lookup"><span data-stu-id="9024d-186">Defines the security capabilities for the <xref:System.ServiceModel.Configuration.NetTcpBindingElement>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9024d-187">备注</span><span class="sxs-lookup"><span data-stu-id="9024d-187">Remarks</span></span>  
 <span data-ttu-id="9024d-188">消息使用消息级安全性实现 SOAP 消息的完整性和保密性，还用于通信对等方的相互身份验证。</span><span class="sxs-lookup"><span data-stu-id="9024d-188">Message uses message-level security for the integrity and confidentiality of the SOAP message, and for mutual authentication of the communication peers.</span></span> <span data-ttu-id="9024d-189">如果在绑定上选择此安全模式，则使用消息安全性绑定元素配置信道堆栈，并且 SOAP 消息可按照 WS-Security* 标准进行保护。</span><span class="sxs-lookup"><span data-stu-id="9024d-189">If this security mode is selected on a binding, the channel stack is configured with message security binding elements and the SOAP messages are secured in compliance with WS-Security* standards.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9024d-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9024d-190">See Also</span></span>  
 <xref:System.ServiceModel.MessageSecurityOverTcp>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetTcpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="9024d-191">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="9024d-191">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9024d-192">绑定</span><span class="sxs-lookup"><span data-stu-id="9024d-192">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9024d-193">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="9024d-193">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9024d-194">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="9024d-194">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9024d-195">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9024d-195">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
