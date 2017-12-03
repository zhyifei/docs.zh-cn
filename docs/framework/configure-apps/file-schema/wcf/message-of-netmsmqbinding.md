---
title: "&lt;netMsmqBinding&gt; 的 &lt;message&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d91d97a27c06e8e6e3ab624c45c6853b1cc23e8f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="0c3c4-102">&lt;netMsmqBinding&gt; 的 &lt;message&gt;</span><span class="sxs-lookup"><span data-stu-id="0c3c4-102">&lt;message&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="0c3c4-103">在此 `netMsmqBinding` 绑定上定义 SOAP 消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>  
  
 <span data-ttu-id="0c3c4-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0c3c4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c3c4-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="0c3c4-105">\<bindings></span></span>  
<span data-ttu-id="0c3c4-106">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="0c3c4-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="0c3c4-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="0c3c4-107">\<binding></span></span>  
<span data-ttu-id="0c3c4-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="0c3c4-108">\<security></span></span>  
<span data-ttu-id="0c3c4-109">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="0c3c4-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c3c4-110">语法</span><span class="sxs-lookup"><span data-stu-id="0c3c4-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c3c4-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0c3c4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0c3c4-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c3c4-113">特性</span><span class="sxs-lookup"><span data-stu-id="0c3c4-113">Attributes</span></span>  
  
|<span data-ttu-id="0c3c4-114">特性</span><span class="sxs-lookup"><span data-stu-id="0c3c4-114">Attribute</span></span>|<span data-ttu-id="0c3c4-115">描述</span><span class="sxs-lookup"><span data-stu-id="0c3c4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c3c4-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="0c3c4-116">algorithmSuite</span></span>|<span data-ttu-id="0c3c4-117">设置消息加密和密钥包装算法，这些算法用于针对通过 MSMQ 传输发送的消息实现基于消息的安全性。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="0c3c4-118">默认值为 `Aes256`。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-118">The default value is `Aes256`.</span></span> <span data-ttu-id="0c3c4-119">此属性的类型为 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|  
|<span data-ttu-id="0c3c4-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="0c3c4-120">clientCredentialType</span></span>|<span data-ttu-id="0c3c4-121">指定针对通过 MSMQ 传输发送的消息执行客户端身份验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="0c3c4-122">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="0c3c4-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0c3c4-123">-None： 允许服务与匿名客户端交互。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="0c3c4-124">服务和客户端都不需要凭据。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="0c3c4-125">-Windows： 使 SOAP 交换在已通过身份验证的 Windows 凭据上下文。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="0c3c4-126">此设置总是执行基于 Kerberos 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="0c3c4-127">-UserName： 使服务可以要求客户端进行身份验证使用 UserName 凭据。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="0c3c4-128">在这种情况下，凭据需要指定使用`clientCredentials`行为**警告：** [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]不支持发送密码摘要或派生密钥使用的密码，并使用这样的密钥来提供消息安全性。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="0c3c4-129">因此，在使用 UserName 凭据时，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 将确保交换的安全性。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-129">Therefore, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="0c3c4-130">此模式要求使用 `clientCredential` 行为和 `serviceCertificate` 在客户端指定服务证书。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="0c3c4-131">-Certificate： 使服务可以要求客户端进行身份验证使用的证书。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="0c3c4-132">在此情况下，需要使用 `clientCredentials` 行为指定客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="0c3c4-133">在此情况下，需要使用 `clientCredentials` 行为，通过指定 `serviceCertificate` 来指定服务凭据。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="0c3c4-134">-CardSpace： 允许服务要求客户端进行身份验证使用 CardSpace。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="0c3c4-135">必须在 `serviceCertiifcate` 行为中设置 `clientCredential`。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-135">The `serviceCertiifcate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="0c3c4-136">默认值为 `Windows`。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-136">The default value is `Windows`.</span></span> <span data-ttu-id="0c3c4-137">此属性的类型为 <xref:System.ServiceModel.MessageCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c3c4-138">子元素</span><span class="sxs-lookup"><span data-stu-id="0c3c4-138">Child Elements</span></span>  
 <span data-ttu-id="0c3c4-139">无</span><span class="sxs-lookup"><span data-stu-id="0c3c4-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c3c4-140">父元素</span><span class="sxs-lookup"><span data-stu-id="0c3c4-140">Parent Elements</span></span>  
  
|<span data-ttu-id="0c3c4-141">元素</span><span class="sxs-lookup"><span data-stu-id="0c3c4-141">Element</span></span>|<span data-ttu-id="0c3c4-142">描述</span><span class="sxs-lookup"><span data-stu-id="0c3c4-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c3c4-143">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="0c3c4-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="0c3c4-144">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="0c3c4-144">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c3c4-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c3c4-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [<span data-ttu-id="0c3c4-146">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="0c3c4-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="0c3c4-147">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="0c3c4-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="0c3c4-148">绑定</span><span class="sxs-lookup"><span data-stu-id="0c3c4-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="0c3c4-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="0c3c4-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="0c3c4-150">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="0c3c4-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="0c3c4-151">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="0c3c4-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
