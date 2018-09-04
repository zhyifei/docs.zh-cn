---
title: '&lt;netMsmqBinding&gt; 的 &lt;message&gt;'
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 65a8b0fa120d23931ad218ac67846c066b050af8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515809"
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="1fe05-102">&lt;netMsmqBinding&gt; 的 &lt;message&gt;</span><span class="sxs-lookup"><span data-stu-id="1fe05-102">&lt;message&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="1fe05-103">在此 `netMsmqBinding` 绑定上定义 SOAP 消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="1fe05-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>  
  
 <span data-ttu-id="1fe05-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1fe05-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1fe05-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="1fe05-105">\<bindings></span></span>  
<span data-ttu-id="1fe05-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="1fe05-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="1fe05-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="1fe05-107">\<binding></span></span>  
<span data-ttu-id="1fe05-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="1fe05-108">\<security></span></span>  
<span data-ttu-id="1fe05-109">\<message></span><span class="sxs-lookup"><span data-stu-id="1fe05-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fe05-110">语法</span><span class="sxs-lookup"><span data-stu-id="1fe05-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fe05-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1fe05-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1fe05-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1fe05-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fe05-113">特性</span><span class="sxs-lookup"><span data-stu-id="1fe05-113">Attributes</span></span>  
  
|<span data-ttu-id="1fe05-114">特性</span><span class="sxs-lookup"><span data-stu-id="1fe05-114">Attribute</span></span>|<span data-ttu-id="1fe05-115">描述</span><span class="sxs-lookup"><span data-stu-id="1fe05-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1fe05-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="1fe05-116">algorithmSuite</span></span>|<span data-ttu-id="1fe05-117">设置消息加密和密钥包装算法，这些算法用于针对通过 MSMQ 传输发送的消息实现基于消息的安全性。</span><span class="sxs-lookup"><span data-stu-id="1fe05-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="1fe05-118">默认值为 `Aes256`。</span><span class="sxs-lookup"><span data-stu-id="1fe05-118">The default value is `Aes256`.</span></span> <span data-ttu-id="1fe05-119">此属性的类型为 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>。</span><span class="sxs-lookup"><span data-stu-id="1fe05-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|  
|<span data-ttu-id="1fe05-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="1fe05-120">clientCredentialType</span></span>|<span data-ttu-id="1fe05-121">指定针对通过 MSMQ 传输发送的消息执行客户端身份验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="1fe05-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="1fe05-122">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="1fe05-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1fe05-123">-None： 此值允许服务与匿名客户端交互。</span><span class="sxs-lookup"><span data-stu-id="1fe05-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="1fe05-124">服务和客户端都不需要凭据。</span><span class="sxs-lookup"><span data-stu-id="1fe05-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="1fe05-125">-Windows： 这使经过身份验证的 Windows 凭据上下文中进行 SOAP 交换。</span><span class="sxs-lookup"><span data-stu-id="1fe05-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="1fe05-126">此设置总是执行基于 Kerberos 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="1fe05-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="1fe05-127">-UserName： 使服务可以要求客户端进行身份验证使用用户名凭据。</span><span class="sxs-lookup"><span data-stu-id="1fe05-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="1fe05-128">在这种情况下需要使用指定凭据`clientCredentials`行为**警告：** Windows Communication Foundation (WCF) 不支持发送密码摘要，也派生密钥密码并使用此类密钥消息安全。</span><span class="sxs-lookup"><span data-stu-id="1fe05-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="1fe05-129">因此，WCF 强制使用 UserName 凭据时，交换的安全性。</span><span class="sxs-lookup"><span data-stu-id="1fe05-129">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="1fe05-130">此模式要求使用 `clientCredential` 行为和 `serviceCertificate` 在客户端指定服务证书。</span><span class="sxs-lookup"><span data-stu-id="1fe05-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="1fe05-131">-Certificate： 使服务可以要求客户端进行身份验证使用的证书。</span><span class="sxs-lookup"><span data-stu-id="1fe05-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="1fe05-132">在此情况下，需要使用 `clientCredentials` 行为指定客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="1fe05-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="1fe05-133">在此情况下，需要使用 `clientCredentials` 行为，通过指定 `serviceCertificate` 来指定服务凭据。</span><span class="sxs-lookup"><span data-stu-id="1fe05-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="1fe05-134">-CardSpace： 允许服务要求客户端进行身份验证使用 CardSpace。</span><span class="sxs-lookup"><span data-stu-id="1fe05-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="1fe05-135">必须在 `serviceCertiifcate` 行为中设置 `clientCredential`。</span><span class="sxs-lookup"><span data-stu-id="1fe05-135">The `serviceCertiifcate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="1fe05-136">默认值为 `Windows`。</span><span class="sxs-lookup"><span data-stu-id="1fe05-136">The default value is `Windows`.</span></span> <span data-ttu-id="1fe05-137">此属性的类型为 <xref:System.ServiceModel.MessageCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="1fe05-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fe05-138">子元素</span><span class="sxs-lookup"><span data-stu-id="1fe05-138">Child Elements</span></span>  
 <span data-ttu-id="1fe05-139">无</span><span class="sxs-lookup"><span data-stu-id="1fe05-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1fe05-140">父元素</span><span class="sxs-lookup"><span data-stu-id="1fe05-140">Parent Elements</span></span>  
  
|<span data-ttu-id="1fe05-141">元素</span><span class="sxs-lookup"><span data-stu-id="1fe05-141">Element</span></span>|<span data-ttu-id="1fe05-142">描述</span><span class="sxs-lookup"><span data-stu-id="1fe05-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fe05-143">\<security></span><span class="sxs-lookup"><span data-stu-id="1fe05-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="1fe05-144">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="1fe05-144">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fe05-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fe05-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [<span data-ttu-id="1fe05-146">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="1fe05-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="1fe05-147">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="1fe05-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1fe05-148">绑定</span><span class="sxs-lookup"><span data-stu-id="1fe05-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1fe05-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="1fe05-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1fe05-150">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="1fe05-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="1fe05-151">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="1fe05-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
