---
title: <message> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736756"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="0f68f-102">\<消息 > \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="0f68f-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="0f68f-103">在此 `netMsmqBinding` 绑定上定义 SOAP 消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="0f68f-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="0f68f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f68f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f68f-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="0f68f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0f68f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0f68f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="0f68f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0f68f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="0f68f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="0f68f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0f68f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-of-netmsmqbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="0f68f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="0f68f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**消息 >**</span><span class="sxs-lookup"><span data-stu-id="0f68f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="0f68f-111">语法</span><span class="sxs-lookup"><span data-stu-id="0f68f-111">Syntax</span></span>

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f68f-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0f68f-112">Attributes and Elements</span></span>

<span data-ttu-id="0f68f-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0f68f-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f68f-114">特性</span><span class="sxs-lookup"><span data-stu-id="0f68f-114">Attributes</span></span>

|<span data-ttu-id="0f68f-115">特性</span><span class="sxs-lookup"><span data-stu-id="0f68f-115">Attribute</span></span>|<span data-ttu-id="0f68f-116">描述</span><span class="sxs-lookup"><span data-stu-id="0f68f-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0f68f-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="0f68f-117">algorithmSuite</span></span>|<span data-ttu-id="0f68f-118">设置消息加密和密钥包装算法，这些算法用于针对通过 MSMQ 传输发送的消息实现基于消息的安全性。</span><span class="sxs-lookup"><span data-stu-id="0f68f-118">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="0f68f-119">默认值为 `Aes256`。</span><span class="sxs-lookup"><span data-stu-id="0f68f-119">The default value is `Aes256`.</span></span> <span data-ttu-id="0f68f-120">此属性的类型为 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>。</span><span class="sxs-lookup"><span data-stu-id="0f68f-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="0f68f-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="0f68f-121">clientCredentialType</span></span>|<span data-ttu-id="0f68f-122">指定针对通过 MSMQ 传输发送的消息执行客户端身份验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="0f68f-122">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="0f68f-123">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="0f68f-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0f68f-124">-None：这允许服务与匿名客户端交互。</span><span class="sxs-lookup"><span data-stu-id="0f68f-124">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="0f68f-125">服务和客户端都不需要凭据。</span><span class="sxs-lookup"><span data-stu-id="0f68f-125">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="0f68f-126">-Windows：这使得 SOAP 交换在 Windows 凭据的已验证上下文下。</span><span class="sxs-lookup"><span data-stu-id="0f68f-126">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="0f68f-127">此设置总是执行基于 Kerberos 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="0f68f-127">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="0f68f-128">-UserName：这使服务可以要求使用用户名凭据对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0f68f-128">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="0f68f-129">在这种情况下，需要使用 `clientCredentials` 行为指定凭据 **：** WINDOWS COMMUNICATION FOUNDATION （WCF）不支持发送密码摘要，也不支持使用密码派生密钥并使用此类密钥来实现消息安全性。</span><span class="sxs-lookup"><span data-stu-id="0f68f-129">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="0f68f-130">因此，在使用用户名凭据时，WCF 会强制使用交换。</span><span class="sxs-lookup"><span data-stu-id="0f68f-130">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="0f68f-131">此模式要求使用 `clientCredential` 行为和 `serviceCertificate` 在客户端指定服务证书。</span><span class="sxs-lookup"><span data-stu-id="0f68f-131">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="0f68f-132">-Certificate：使服务可以要求使用证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0f68f-132">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="0f68f-133">在此情况下，需要使用 `clientCredentials` 行为指定客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="0f68f-133">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="0f68f-134">在此情况下，需要使用 `clientCredentials` 行为，通过指定 `serviceCertificate` 来指定服务凭据。</span><span class="sxs-lookup"><span data-stu-id="0f68f-134">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="0f68f-135">-CardSpace：这允许服务要求使用 CardSpace 对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0f68f-135">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="0f68f-136">必须在 `serviceCertificate` 行为中设置 `clientCredential`。</span><span class="sxs-lookup"><span data-stu-id="0f68f-136">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="0f68f-137">默认值为 `Windows`。</span><span class="sxs-lookup"><span data-stu-id="0f68f-137">The default value is `Windows`.</span></span> <span data-ttu-id="0f68f-138">此属性的类型为 <xref:System.ServiceModel.MessageCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="0f68f-138">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0f68f-139">子元素</span><span class="sxs-lookup"><span data-stu-id="0f68f-139">Child Elements</span></span>

<span data-ttu-id="0f68f-140">None</span><span class="sxs-lookup"><span data-stu-id="0f68f-140">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0f68f-141">父元素</span><span class="sxs-lookup"><span data-stu-id="0f68f-141">Parent Elements</span></span>

|<span data-ttu-id="0f68f-142">元素</span><span class="sxs-lookup"><span data-stu-id="0f68f-142">Element</span></span>|<span data-ttu-id="0f68f-143">描述</span><span class="sxs-lookup"><span data-stu-id="0f68f-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f68f-144">\<security ></span><span class="sxs-lookup"><span data-stu-id="0f68f-144">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="0f68f-145">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="0f68f-145">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="0f68f-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f68f-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="0f68f-147">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="0f68f-147">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="0f68f-148">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="0f68f-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0f68f-149">绑定</span><span class="sxs-lookup"><span data-stu-id="0f68f-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0f68f-150">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="0f68f-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0f68f-151">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="0f68f-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0f68f-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="0f68f-152">\<binding></span></span>](bindings.md)
