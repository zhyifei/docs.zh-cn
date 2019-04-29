---
title: <message> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: c623b7daf1e91c9c1800b9653525cd51b1087506
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768948"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="560c5-102">\<message> of \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="560c5-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="560c5-103">在此 `netMsmqBinding` 绑定上定义 SOAP 消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="560c5-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a><span data-ttu-id="560c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="560c5-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="560c5-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="560c5-105">Attributes and Elements</span></span>

<span data-ttu-id="560c5-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="560c5-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="560c5-107">特性</span><span class="sxs-lookup"><span data-stu-id="560c5-107">Attributes</span></span>

|<span data-ttu-id="560c5-108">特性</span><span class="sxs-lookup"><span data-stu-id="560c5-108">Attribute</span></span>|<span data-ttu-id="560c5-109">描述</span><span class="sxs-lookup"><span data-stu-id="560c5-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="560c5-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="560c5-110">algorithmSuite</span></span>|<span data-ttu-id="560c5-111">设置消息加密和密钥包装算法，这些算法用于针对通过 MSMQ 传输发送的消息实现基于消息的安全性。</span><span class="sxs-lookup"><span data-stu-id="560c5-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="560c5-112">默认值为 `Aes256`。</span><span class="sxs-lookup"><span data-stu-id="560c5-112">The default value is `Aes256`.</span></span> <span data-ttu-id="560c5-113">此属性的类型为 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>。</span><span class="sxs-lookup"><span data-stu-id="560c5-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="560c5-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="560c5-114">clientCredentialType</span></span>|<span data-ttu-id="560c5-115">指定针对通过 MSMQ 传输发送的消息执行客户端身份验证时要使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="560c5-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="560c5-116">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="560c5-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="560c5-117">-None:允许服务与匿名客户端交互。</span><span class="sxs-lookup"><span data-stu-id="560c5-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="560c5-118">服务和客户端都不需要凭据。</span><span class="sxs-lookup"><span data-stu-id="560c5-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="560c5-119">-Windows:这使经过身份验证的 Windows 凭据上下文中进行 SOAP 交换。</span><span class="sxs-lookup"><span data-stu-id="560c5-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="560c5-120">此设置总是执行基于 Kerberos 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="560c5-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="560c5-121">-UserName:这使服务可以要求客户端进行身份验证使用用户名凭据。</span><span class="sxs-lookup"><span data-stu-id="560c5-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="560c5-122">在这种情况下需要使用指定凭据`clientCredentials`行为**警告：** Windows Communication Foundation (WCF) 不支持发送密码摘要，也派生密钥使用的密码并使用此类密钥来提供消息安全性。</span><span class="sxs-lookup"><span data-stu-id="560c5-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="560c5-123">因此，WCF 强制使用 UserName 凭据时，交换的安全性。</span><span class="sxs-lookup"><span data-stu-id="560c5-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="560c5-124">此模式要求使用 `clientCredential` 行为和 `serviceCertificate` 在客户端指定服务证书。</span><span class="sxs-lookup"><span data-stu-id="560c5-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="560c5-125">-证书：这使服务可以要求客户端进行身份验证使用的证书。</span><span class="sxs-lookup"><span data-stu-id="560c5-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="560c5-126">在此情况下，需要使用 `clientCredentials` 行为指定客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="560c5-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="560c5-127">在此情况下，需要使用 `clientCredentials` 行为，通过指定 `serviceCertificate` 来指定服务凭据。</span><span class="sxs-lookup"><span data-stu-id="560c5-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="560c5-128">-CardSpace:这允许服务要求客户端进行身份验证使用 CardSpace。</span><span class="sxs-lookup"><span data-stu-id="560c5-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="560c5-129">必须在 `serviceCertificate` 行为中设置 `clientCredential`。</span><span class="sxs-lookup"><span data-stu-id="560c5-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="560c5-130">默认值为 `Windows`。</span><span class="sxs-lookup"><span data-stu-id="560c5-130">The default value is `Windows`.</span></span> <span data-ttu-id="560c5-131">此属性的类型为 <xref:System.ServiceModel.MessageCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="560c5-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="560c5-132">子元素</span><span class="sxs-lookup"><span data-stu-id="560c5-132">Child Elements</span></span>

<span data-ttu-id="560c5-133">None</span><span class="sxs-lookup"><span data-stu-id="560c5-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="560c5-134">父元素</span><span class="sxs-lookup"><span data-stu-id="560c5-134">Parent Elements</span></span>

|<span data-ttu-id="560c5-135">元素</span><span class="sxs-lookup"><span data-stu-id="560c5-135">Element</span></span>|<span data-ttu-id="560c5-136">描述</span><span class="sxs-lookup"><span data-stu-id="560c5-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="560c5-137">\<security></span><span class="sxs-lookup"><span data-stu-id="560c5-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="560c5-138">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="560c5-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="560c5-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="560c5-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="560c5-140">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="560c5-140">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="560c5-141">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="560c5-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="560c5-142">绑定</span><span class="sxs-lookup"><span data-stu-id="560c5-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="560c5-143">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="560c5-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="560c5-144">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="560c5-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="560c5-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="560c5-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
