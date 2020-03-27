---
title: 演练：创建自定义客户端和服务凭据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b5ba5c3-0c6c-48e9-9e46-54acaec443ba
ms.openlocfilehash: ddd9f03e26f7a8345f1070715e4877c533c361fb
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345264"
---
# <a name="walkthrough-creating-custom-client-and-service-credentials"></a><span data-ttu-id="1718c-102">演练：创建自定义客户端和服务凭据</span><span class="sxs-lookup"><span data-stu-id="1718c-102">Walkthrough: Creating Custom Client and Service Credentials</span></span>

<span data-ttu-id="1718c-103">本主题演示如何实现自定义客户端和服务凭据以及如何在应用程序代码中使用自定义凭据。</span><span class="sxs-lookup"><span data-stu-id="1718c-103">This topic shows how to implement custom client and service credentials and how to use custom credentials from application code.</span></span>

## <a name="credentials-extensibility-classes"></a><span data-ttu-id="1718c-104">凭据扩展性类</span><span class="sxs-lookup"><span data-stu-id="1718c-104">Credentials Extensibility Classes</span></span>

<span data-ttu-id="1718c-105"><xref:System.ServiceModel.Description.ClientCredentials>和<xref:System.ServiceModel.Description.ServiceCredentials>类是 Windows 通信基础 （WCF） 安全扩展性的主要入口点。</span><span class="sxs-lookup"><span data-stu-id="1718c-105">The <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes are the main entry points to the Windows Communication Foundation (WCF) security extensibility.</span></span> <span data-ttu-id="1718c-106">这些凭据类提供 API，应用程序代码可以使用这些 API 来设置凭据信息和将凭据类型转换为安全令牌。</span><span class="sxs-lookup"><span data-stu-id="1718c-106">These credentials classes provide the APIs that enable application code to set credentials information and to convert credential types into security tokens.</span></span> <span data-ttu-id="1718c-107">（*安全令牌*是用于在 SOAP 消息中传输凭据信息的窗体。这些凭据类的职责可以分为两个方面：</span><span class="sxs-lookup"><span data-stu-id="1718c-107">(*Security tokens* are the form used to transmit credential information inside SOAP messages.) The responsibilities of these credentials classes can be divided into two areas:</span></span>

- <span data-ttu-id="1718c-108">为应用程序提供 API 以设置凭据信息。</span><span class="sxs-lookup"><span data-stu-id="1718c-108">Provide the APIs for applications to set credentials information.</span></span>

- <span data-ttu-id="1718c-109">用作 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 实现的工厂。</span><span class="sxs-lookup"><span data-stu-id="1718c-109">Perform as a factory for <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementations.</span></span>

<span data-ttu-id="1718c-110">WCF 中提供的默认实现支持系统提供的凭据类型，并创建能够处理这些凭据类型的安全令牌管理器。</span><span class="sxs-lookup"><span data-stu-id="1718c-110">The default implementations provided in WCF support the system-provided credential types and create a security token manager that is capable of handling those credentials types.</span></span>

## <a name="reasons-to-customize"></a><span data-ttu-id="1718c-111">自定义原因</span><span class="sxs-lookup"><span data-stu-id="1718c-111">Reasons to Customize</span></span>

<span data-ttu-id="1718c-112">自定义客户端或服务凭据类有多种原因。</span><span class="sxs-lookup"><span data-stu-id="1718c-112">There are multiple reasons for customizing either client or service credential classes.</span></span> <span data-ttu-id="1718c-113">最重要的是要求更改处理系统提供的凭据类型的默认 WCF 安全行为，尤其是出于以下原因：</span><span class="sxs-lookup"><span data-stu-id="1718c-113">Foremost is the requirement to change the default WCF security behavior with regard to handling system-provided credential types, especially for the following reasons:</span></span>

- <span data-ttu-id="1718c-114">无法使用其他扩展点进行的更改。</span><span class="sxs-lookup"><span data-stu-id="1718c-114">Changes that are not possible using other extensibility points.</span></span>

- <span data-ttu-id="1718c-115">添加新的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="1718c-115">Adding new credential types.</span></span>

- <span data-ttu-id="1718c-116">添加新的自定义安全令牌类型。</span><span class="sxs-lookup"><span data-stu-id="1718c-116">Adding new custom security token types.</span></span>

<span data-ttu-id="1718c-117">本主题说明如何实现自定义客户端和服务凭据以及如何在应用程序代码中使用它们。</span><span class="sxs-lookup"><span data-stu-id="1718c-117">This topic describes how to implement custom client and service credentials and how to use them from application code.</span></span>

## <a name="first-in-a-series"></a><span data-ttu-id="1718c-118">系列主题中的第一个主题</span><span class="sxs-lookup"><span data-stu-id="1718c-118">First in a Series</span></span>

<span data-ttu-id="1718c-119">创建自定义凭据类只是第一步，因为自定义凭据的原因是更改有关凭据预配、安全令牌序列化或身份验证的 WCF 行为。</span><span class="sxs-lookup"><span data-stu-id="1718c-119">Creating a custom credentials class is only the first step, because the reason for customizing credentials is to change WCF behavior regarding credentials provisioning, security token serialization, or authentication.</span></span> <span data-ttu-id="1718c-120">本节中的其他主题说明如何创建自定义序列化程序和身份验证器。</span><span class="sxs-lookup"><span data-stu-id="1718c-120">Other topics in this section describe how to create custom serializers and authenticators.</span></span> <span data-ttu-id="1718c-121">在这一方面，创建自定义凭据类是系列主题中的第一个主题。</span><span class="sxs-lookup"><span data-stu-id="1718c-121">In this regard, creating custom credential class is the first topic in the series.</span></span> <span data-ttu-id="1718c-122">后续操作（创建自定义序列化程序和身份验证器）只有在创建自定义凭据后才能进行。</span><span class="sxs-lookup"><span data-stu-id="1718c-122">Subsequent actions (creating custom serializers and authenticators) can be done only after creating custom credentials.</span></span> <span data-ttu-id="1718c-123">基于本主题的其他主题包括：</span><span class="sxs-lookup"><span data-stu-id="1718c-123">Additional topics that build upon this topic include:</span></span>

- [<span data-ttu-id="1718c-124">如何：创建自定义安全令牌提供程序</span><span class="sxs-lookup"><span data-stu-id="1718c-124">How to: Create a Custom Security Token Provider</span></span>](how-to-create-a-custom-security-token-provider.md)

- [<span data-ttu-id="1718c-125">如何：创建自定义安全令牌身份验证器</span><span class="sxs-lookup"><span data-stu-id="1718c-125">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)

- <span data-ttu-id="1718c-126">[如何：创建自定义令牌](how-to-create-a-custom-token.md)。</span><span class="sxs-lookup"><span data-stu-id="1718c-126">[How to: Create a Custom Token](how-to-create-a-custom-token.md).</span></span>

## <a name="procedures"></a><span data-ttu-id="1718c-127">过程</span><span class="sxs-lookup"><span data-stu-id="1718c-127">Procedures</span></span>

#### <a name="to-implement-custom-client-credentials"></a><span data-ttu-id="1718c-128">实现自定义客户端凭据</span><span class="sxs-lookup"><span data-stu-id="1718c-128">To implement custom client credentials</span></span>

1. <span data-ttu-id="1718c-129">定义一个从 <xref:System.ServiceModel.Description.ClientCredentials> 类派生的新类。</span><span class="sxs-lookup"><span data-stu-id="1718c-129">Define a new class derived from the <xref:System.ServiceModel.Description.ClientCredentials> class.</span></span>

2. <span data-ttu-id="1718c-130">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-130">Optional.</span></span> <span data-ttu-id="1718c-131">为新凭据类型添加新方法或新属性。</span><span class="sxs-lookup"><span data-stu-id="1718c-131">Add new methods or properties for new credential types.</span></span> <span data-ttu-id="1718c-132">如果未添加新凭据类型，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="1718c-132">If you do not add new credential types, skip this step.</span></span> <span data-ttu-id="1718c-133">下面的示例添加 `CreditCardNumber` 属性。</span><span class="sxs-lookup"><span data-stu-id="1718c-133">The following example adds a `CreditCardNumber` property.</span></span>

3. <span data-ttu-id="1718c-134">重写 <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-134">Override the <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> method.</span></span> <span data-ttu-id="1718c-135">使用自定义客户端凭据时，WCF 安全基础结构会自动调用此方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-135">This method is automatically called by WCF security infrastructure when the custom client credential is used.</span></span> <span data-ttu-id="1718c-136">此方法负责创建和返回 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 类实现的实例。</span><span class="sxs-lookup"><span data-stu-id="1718c-136">This method is responsible for creating and returning an instance of an implementation of the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1718c-137">需要特别注意的是，将重写 <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> 方法以创建自定义安全令牌管理器。</span><span class="sxs-lookup"><span data-stu-id="1718c-137">It is important to note that the <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> method is overridden to create a custom security token manager.</span></span> <span data-ttu-id="1718c-138">派生自 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 的安全令牌管理器必须返回派生自 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 的自定义安全令牌提供程序，才能创建实际的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="1718c-138">The security token manager, derived from <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, must return a custom security token provider, derived from <xref:System.IdentityModel.Selectors.SecurityTokenProvider>, to create the actual security token.</span></span> <span data-ttu-id="1718c-139">如果不遵循此模式创建安全令牌，则当缓存 <xref:System.ServiceModel.ChannelFactory> 对象（这是 WCF 客户端代理的默认行为）时，您的应用程序可能无法正常工作，从而可能会导致面临特权提升攻击。</span><span class="sxs-lookup"><span data-stu-id="1718c-139">If you do not follow this pattern for creating security tokens, your application may function incorrectly when <xref:System.ServiceModel.ChannelFactory> objects are cached (which is the default behavior for WCF client proxies), potentially resulting in an elevation of privilege attack.</span></span> <span data-ttu-id="1718c-140">自定义凭据对象将作为 <xref:System.ServiceModel.ChannelFactory> 的一部分进行缓存。</span><span class="sxs-lookup"><span data-stu-id="1718c-140">The custom credential object is cached as part of the <xref:System.ServiceModel.ChannelFactory>.</span></span> <span data-ttu-id="1718c-141">然而，在每次调用时都会创建自定义 <xref:System.IdentityModel.Selectors.SecurityTokenManager>，只要在 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 中放置了令牌创建逻辑，它就可以缓解安全威胁。</span><span class="sxs-lookup"><span data-stu-id="1718c-141">However, the custom <xref:System.IdentityModel.Selectors.SecurityTokenManager> is created on every invocation, which mitigates the security threat as long as the token creation logic is placed in the <xref:System.IdentityModel.Selectors.SecurityTokenManager>.</span></span>

4. <span data-ttu-id="1718c-142">重写 <xref:System.ServiceModel.Description.ClientCredentials.CloneCore%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-142">Override the <xref:System.ServiceModel.Description.ClientCredentials.CloneCore%2A> method.</span></span>

    [!code-csharp[c_CustomCredentials#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#1)]
    [!code-vb[c_CustomCredentials#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#1)]

#### <a name="to-implement-a-custom-client-security-token-manager"></a><span data-ttu-id="1718c-143">实现自定义客户端安全令牌管理器</span><span class="sxs-lookup"><span data-stu-id="1718c-143">To implement a custom client security token manager</span></span>

1. <span data-ttu-id="1718c-144">定义一个从 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 派生的新类。</span><span class="sxs-lookup"><span data-stu-id="1718c-144">Define a new class derived from <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.</span></span>

2. <span data-ttu-id="1718c-145">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-145">Optional.</span></span> <span data-ttu-id="1718c-146">如果必须创建一个自定义 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> 实现，则重写 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-146">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method if a custom <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation must be created.</span></span> <span data-ttu-id="1718c-147">有关自定义安全令牌提供程序的详细信息，请参阅[如何：创建自定义安全令牌提供程序](how-to-create-a-custom-security-token-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="1718c-147">For more information about custom security token providers, see [How to: Create a Custom Security Token Provider](how-to-create-a-custom-security-token-provider.md).</span></span>

3. <span data-ttu-id="1718c-148">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-148">Optional.</span></span> <span data-ttu-id="1718c-149">如果必须创建一个自定义 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%28System.IdentityModel.Selectors.SecurityTokenRequirement%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%40%29> 实现，则重写 <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-149">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%28System.IdentityModel.Selectors.SecurityTokenRequirement%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%40%29> method if a custom <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> implementation must be created.</span></span> <span data-ttu-id="1718c-150">有关自定义安全令牌身份验证器的详细信息，请参阅[如何：创建自定义安全令牌身份验证器](how-to-create-a-custom-security-token-authenticator.md)。</span><span class="sxs-lookup"><span data-stu-id="1718c-150">For more information about custom security token authenticators, see [How to: Create a Custom Security Token Authenticator](how-to-create-a-custom-security-token-authenticator.md).</span></span>

4. <span data-ttu-id="1718c-151">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-151">Optional.</span></span> <span data-ttu-id="1718c-152">如果必须创建一个自定义 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%2A>，则重写 <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-152">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%2A> method if a custom <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> must be created.</span></span> <span data-ttu-id="1718c-153">有关自定义安全令牌和自定义安全令牌序列化器的详细信息，请参阅[如何：创建自定义令牌](how-to-create-a-custom-token.md)。</span><span class="sxs-lookup"><span data-stu-id="1718c-153">For more information about custom security tokens and custom security token serializers, see [How to: Create a Custom Token](how-to-create-a-custom-token.md).</span></span>

    [!code-csharp[c_CustomCredentials#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#2)]
    [!code-vb[c_CustomCredentials#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#2)]

#### <a name="to-use-a-custom-client-credentials-from-application-code"></a><span data-ttu-id="1718c-154">在应用程序代码中使用自定义客户端凭据</span><span class="sxs-lookup"><span data-stu-id="1718c-154">To use a custom client credentials from application code</span></span>

1. <span data-ttu-id="1718c-155">创建生成的表示服务接口的客户端的实例，或创建指向要与之通信的服务的 <xref:System.ServiceModel.ChannelFactory> 的实例。</span><span class="sxs-lookup"><span data-stu-id="1718c-155">Either create an instance of the generated client that represents the service interface, or create an instance of the <xref:System.ServiceModel.ChannelFactory> pointing to a service you want to communicate with.</span></span>

2. <span data-ttu-id="1718c-156">从 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 集合中删除系统提供的客户端凭据行为，此集合可以通过 <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> 属性访问。</span><span class="sxs-lookup"><span data-stu-id="1718c-156">Remove the system-provided client credentials behavior from the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> collection, which can be accessed through the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property.</span></span>

3. <span data-ttu-id="1718c-157">创建自定义客户端凭据类的一个新实例并将其添加到 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 集合中，此集合可以通过 <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> 属性访问。</span><span class="sxs-lookup"><span data-stu-id="1718c-157">Create a new instance of a custom client credentials class and add it to the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> collection, which can be accessed through the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property.</span></span>

    [!code-csharp[c_CustomCredentials#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#3)]
    [!code-vb[c_CustomCredentials#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#3)]

<span data-ttu-id="1718c-158">前面的过程演示如何从应用程序代码中使用客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="1718c-158">The previous procedure shows how to use client credentials from application code.</span></span> <span data-ttu-id="1718c-159">也可以使用应用程序配置文件配置 WCF 凭据。</span><span class="sxs-lookup"><span data-stu-id="1718c-159">WCF credentials can also be configured using the application configuration file.</span></span> <span data-ttu-id="1718c-160">使用应用程序配置通常比硬编码更可取，因为它允许更改应用程序参数而无需更改源代码、重新编译和重新部署。</span><span class="sxs-lookup"><span data-stu-id="1718c-160">Using application configuration is often preferable to hard-coding because it enables modification of application parameters without having to modify the source, recompiling, and redeployment.</span></span>

<span data-ttu-id="1718c-161">下一个过程说明如何为配置自定义凭据提供支持。</span><span class="sxs-lookup"><span data-stu-id="1718c-161">The next procedure describes how to provide support for configuration of custom credentials.</span></span>

#### <a name="creating-a-configuration-handler-for-custom-client-credentials"></a><span data-ttu-id="1718c-162">创建自定义客户端凭据的配置处理程序</span><span class="sxs-lookup"><span data-stu-id="1718c-162">Creating a configuration handler for custom client credentials</span></span>

1. <span data-ttu-id="1718c-163">定义一个从 <xref:System.ServiceModel.Configuration.ClientCredentialsElement> 派生的新类。</span><span class="sxs-lookup"><span data-stu-id="1718c-163">Define a new class derived from <xref:System.ServiceModel.Configuration.ClientCredentialsElement>.</span></span>

2. <span data-ttu-id="1718c-164">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-164">Optional.</span></span> <span data-ttu-id="1718c-165">为所有其他要通过应用程序配置公开的配置参数添加属性。</span><span class="sxs-lookup"><span data-stu-id="1718c-165">Add properties for all additional configuration parameters that you want to expose through application configuration.</span></span> <span data-ttu-id="1718c-166">下面的示例添加一个名为 `CreditCardNumber` 的属性。</span><span class="sxs-lookup"><span data-stu-id="1718c-166">The example below adds one property named `CreditCardNumber`.</span></span>

3. <span data-ttu-id="1718c-167">重写 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.BehaviorType%2A> 属性以返回使用配置元素创建的自定义客户端凭据类的类型。</span><span class="sxs-lookup"><span data-stu-id="1718c-167">Override the <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.BehaviorType%2A> property to return the type of the custom client credentials class created with the configuration element.</span></span>

4. <span data-ttu-id="1718c-168">重写 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.CreateBehavior%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-168">Override the <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.CreateBehavior%2A> method.</span></span> <span data-ttu-id="1718c-169">此方法负责根据从配置文件加载的设置创建和返回自定义凭据类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="1718c-169">The method is responsible for creating and returning an instance of the custom credential class based on the settings loaded from the configuration file.</span></span> <span data-ttu-id="1718c-170">从此方法中调用基 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ApplyConfiguration%28System.ServiceModel.Description.ClientCredentials%29> 方法以检索加载到客户端凭据实例中的系统提供的凭据设置。</span><span class="sxs-lookup"><span data-stu-id="1718c-170">Call the base <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ApplyConfiguration%28System.ServiceModel.Description.ClientCredentials%29> method from this method to retrieve the system-provided credentials settings loaded into your custom client credentials instance.</span></span>

5. <span data-ttu-id="1718c-171">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-171">Optional.</span></span> <span data-ttu-id="1718c-172">如果您在步骤 2 中添加了其他属性，则需要重写 <xref:System.Configuration.ConfigurationElement.Properties%2A> 属性，以便注册其他配置设置，使配置框架可以识别它们。</span><span class="sxs-lookup"><span data-stu-id="1718c-172">If you added additional properties in step 2, you need to override the <xref:System.Configuration.ConfigurationElement.Properties%2A> property in order to register your additional configuration settings for the configuration framework to recognize them.</span></span> <span data-ttu-id="1718c-173">组合使用您的属性与基类属性可以通过此自定义客户端凭据配置元素来配置系统提供的设置。</span><span class="sxs-lookup"><span data-stu-id="1718c-173">Combine your properties with the base class properties to allow the system-provided settings to be configured through this custom client credentials configuration element.</span></span>

    [!code-csharp[c_CustomCredentials#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#7)]
    [!code-vb[c_CustomCredentials#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#7)]

<span data-ttu-id="1718c-174">获得配置处理程序类后，即可将其集成到 WCF 配置框架中。</span><span class="sxs-lookup"><span data-stu-id="1718c-174">Once you have the configuration handler class, it can be integrated into the WCF configuration framework.</span></span> <span data-ttu-id="1718c-175">这使自定义客户端凭据能够用于客户端终结点行为元素中，如下一个过程所示。</span><span class="sxs-lookup"><span data-stu-id="1718c-175">That enables the custom client credentials to be used in the client endpoint behavior elements, as shown in the next procedure.</span></span>

#### <a name="to-register-and-use-a-custom-client-credentials-configuration-handler-in-the-application-configuration"></a><span data-ttu-id="1718c-176">在应用程序配置中注册和使用自定义客户端凭据配置处理程序</span><span class="sxs-lookup"><span data-stu-id="1718c-176">To register and use a custom client credentials configuration handler in the application configuration</span></span>

1. <span data-ttu-id="1718c-177">向配置文件添加`extensions`<>元素和<>`behaviorExtensions`元素。</span><span class="sxs-lookup"><span data-stu-id="1718c-177">Add an <`extensions`> element and a <`behaviorExtensions`> element to the configuration file.</span></span>

2. <span data-ttu-id="1718c-178">向<>`add``behaviorExtensions`元素添加<>元素，`name`并将属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="1718c-178">Add an <`add`> element to the <`behaviorExtensions`> element and set the `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="1718c-179">将 `type` 特性设置为完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="1718c-179">Set the `type` attribute to the fully-qualified type name.</span></span> <span data-ttu-id="1718c-180">此外还包括程序集名称和其他程序集属性。</span><span class="sxs-lookup"><span data-stu-id="1718c-180">Also include the assembly name and other assembly attributes.</span></span>

    ```xml
    <system.serviceModel>
      <extensions>
        <behaviorExtensions>
          <add name="myClientCredentials" type="Microsoft.ServiceModel.Samples.MyClientCredentialsConfigHandler, CustomCredentials, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
        </behaviorExtensions>
      </extensions>
    </system.serviceModel>
    ```

4. <span data-ttu-id="1718c-181">注册配置处理程序后，可以在相同的配置文件中使用自定义凭据元素，而不是系统提供的<>`clientCredentials`元素。</span><span class="sxs-lookup"><span data-stu-id="1718c-181">After registering your configuration handler, the custom credentials element can be used inside the same configuration file instead of the system-provided <`clientCredentials`> element.</span></span> <span data-ttu-id="1718c-182">可以同时使用系统提供的属性和任何添加到配置处理程序实现的新属性。</span><span class="sxs-lookup"><span data-stu-id="1718c-182">You can use both the system-provided properties and any new properties that you have added to your configuration handler implementation.</span></span> <span data-ttu-id="1718c-183">下面的示例使用 `creditCardNumber` 属性设置自定义属性的值。</span><span class="sxs-lookup"><span data-stu-id="1718c-183">The following example sets the value of a custom property using the `creditCardNumber` attribute.</span></span>

    ```xml
    <behaviors>
      <endpointBehaviors>
        <behavior name="myClientCredentialsBehavior">
          <myClientCredentials creditCardNumber="123-123-123"/>
        </behavior>
      </endpointBehaviors>
    </behaviors>
    ```

#### <a name="to-implement-custom-service-credentials"></a><span data-ttu-id="1718c-184">实现自定义服务凭据</span><span class="sxs-lookup"><span data-stu-id="1718c-184">To implement custom service credentials</span></span>

1. <span data-ttu-id="1718c-185">定义一个从 <xref:System.ServiceModel.Description.ServiceCredentials> 派生的新类。</span><span class="sxs-lookup"><span data-stu-id="1718c-185">Define a new class derived from <xref:System.ServiceModel.Description.ServiceCredentials>.</span></span>

2. <span data-ttu-id="1718c-186">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-186">Optional.</span></span> <span data-ttu-id="1718c-187">添加新属性以为将要添加的新凭据值提供 API。</span><span class="sxs-lookup"><span data-stu-id="1718c-187">Add new properties to provide APIs for new credential values that are being added.</span></span> <span data-ttu-id="1718c-188">如果未添加新凭据值，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="1718c-188">If you do not add new credential values, skip this step.</span></span> <span data-ttu-id="1718c-189">下面的示例添加 `AdditionalCertificate` 属性。</span><span class="sxs-lookup"><span data-stu-id="1718c-189">The following example adds an `AdditionalCertificate` property.</span></span>

3. <span data-ttu-id="1718c-190">重写 <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-190">Override the <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> method.</span></span> <span data-ttu-id="1718c-191">使用自定义客户端凭据时，WCF 基础结构会自动调用此方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-191">This method is automatically called by the WCF infrastructure when the custom client credential is used.</span></span> <span data-ttu-id="1718c-192">此方法负责创建和返回 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 类的实现的实例（在下一个过程中说明）。</span><span class="sxs-lookup"><span data-stu-id="1718c-192">The method is responsible for creating and returning an instance of an implementation of the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class (described in the next procedure).</span></span>

4. <span data-ttu-id="1718c-193">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-193">Optional.</span></span> <span data-ttu-id="1718c-194">重写 <xref:System.ServiceModel.Description.ServiceCredentials.CloneCore%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-194">Override the <xref:System.ServiceModel.Description.ServiceCredentials.CloneCore%2A> method.</span></span> <span data-ttu-id="1718c-195">只有在将新属性或内部字段添加到自定义客户端凭据实现时，才需要此操作。</span><span class="sxs-lookup"><span data-stu-id="1718c-195">This is required only if adding new properties or internal fields to the custom client credentials implementation.</span></span>

    [!code-csharp[c_CustomCredentials#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#4)]
    [!code-vb[c_CustomCredentials#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#4)]

#### <a name="to-implement-a-custom-service-security-token-manager"></a><span data-ttu-id="1718c-196">实现自定义服务安全令牌管理器</span><span class="sxs-lookup"><span data-stu-id="1718c-196">To implement a custom service security token manager</span></span>

1. <span data-ttu-id="1718c-197">定义一个从 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 类派生的新类。</span><span class="sxs-lookup"><span data-stu-id="1718c-197">Define a new class derived from the <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class.</span></span>

2. <span data-ttu-id="1718c-198">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-198">Optional.</span></span> <span data-ttu-id="1718c-199">如果必须创建一个自定义 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%2A> 实现，则重写 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-199">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%2A> method if a custom <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation must be created.</span></span> <span data-ttu-id="1718c-200">有关自定义安全令牌提供程序的详细信息，请参阅[如何：创建自定义安全令牌提供程序](how-to-create-a-custom-security-token-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="1718c-200">For more information about custom security token providers, see [How to: Create a Custom Security Token Provider](how-to-create-a-custom-security-token-provider.md).</span></span>

3. <span data-ttu-id="1718c-201">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-201">Optional.</span></span> <span data-ttu-id="1718c-202">如果必须创建一个自定义 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> 实现，则重写 <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-202">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> method if a custom <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> implementation must be created.</span></span> <span data-ttu-id="1718c-203">有关自定义安全令牌身份验证器的详细信息，请参阅[如何：创建自定义安全令牌身份验证器](how-to-create-a-custom-security-token-authenticator.md)主题。</span><span class="sxs-lookup"><span data-stu-id="1718c-203">For more information about custom security token authenticators, see [How to: Create a Custom Security Token Authenticator](how-to-create-a-custom-security-token-authenticator.md) topic.</span></span>

4. <span data-ttu-id="1718c-204">可选。</span><span class="sxs-lookup"><span data-stu-id="1718c-204">Optional.</span></span> <span data-ttu-id="1718c-205">如果必须创建一个自定义 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%28System.IdentityModel.Selectors.SecurityTokenVersion%29>，则重写 <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> 方法。</span><span class="sxs-lookup"><span data-stu-id="1718c-205">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%28System.IdentityModel.Selectors.SecurityTokenVersion%29> method if a custom <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> must be created.</span></span> <span data-ttu-id="1718c-206">有关自定义安全令牌和自定义安全令牌序列化器的详细信息，请参阅[如何：创建自定义令牌](how-to-create-a-custom-token.md)。</span><span class="sxs-lookup"><span data-stu-id="1718c-206">For more information about custom security tokens and custom security token serializers, see [How to: Create a Custom Token](how-to-create-a-custom-token.md).</span></span>

    [!code-csharp[c_CustomCredentials#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#5)]
    [!code-vb[c_CustomCredentials#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#5)]

#### <a name="to-use-custom-service-credentials-from-application-code"></a><span data-ttu-id="1718c-207">在应用程序代码中使用自定义服务凭据</span><span class="sxs-lookup"><span data-stu-id="1718c-207">To use custom service credentials from application code</span></span>

1. <span data-ttu-id="1718c-208">创建 <xref:System.ServiceModel.ServiceHost> 的实例：</span><span class="sxs-lookup"><span data-stu-id="1718c-208">Create an instance of the <xref:System.ServiceModel.ServiceHost>.</span></span>

2. <span data-ttu-id="1718c-209">从 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 集合中删除系统提供的服务凭据行为。</span><span class="sxs-lookup"><span data-stu-id="1718c-209">Remove the system-provided service credentials behavior from the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection.</span></span>

3. <span data-ttu-id="1718c-210">创建自定义服务凭据类的一个新实例并将其添加到 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 集合中。</span><span class="sxs-lookup"><span data-stu-id="1718c-210">Create a new instance of the custom service credentials class and add it to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection.</span></span>

    [!code-csharp[c_CustomCredentials#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#6)]
    [!code-vb[c_CustomCredentials#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#6)]

<span data-ttu-id="1718c-211">使用过程"和"`To create a configuration handler for custom client credentials`中前面描述的步骤添加对配置的支持。`To register and use a custom client credentials configuration handler in the application configuration`唯一的区别是使用类<xref:System.ServiceModel.Configuration.ServiceCredentialsElement>而不是类<xref:System.ServiceModel.Configuration.ClientCredentialsElement>作为配置处理程序的基础类。</span><span class="sxs-lookup"><span data-stu-id="1718c-211">Add support for configuration using the steps described previously in the procedures "`To create a configuration handler for custom client credentials`" and "`To register and use a custom client credentials configuration handler in the application configuration`." The only difference is to use the <xref:System.ServiceModel.Configuration.ServiceCredentialsElement> class instead of the <xref:System.ServiceModel.Configuration.ClientCredentialsElement> class as a base class for the configuration handler.</span></span> <span data-ttu-id="1718c-212">这样，使用系统提供的 `<serviceCredentials>` 元素的任何地方都可以使用自定义服务凭据元素。</span><span class="sxs-lookup"><span data-stu-id="1718c-212">The custom service credential element can then be used wherever the system-provided `<serviceCredentials>` element is used.</span></span>

## <a name="see-also"></a><span data-ttu-id="1718c-213">请参阅</span><span class="sxs-lookup"><span data-stu-id="1718c-213">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.Security.SecurityCredentialsManager>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- [<span data-ttu-id="1718c-214">如何：创建自定义安全令牌提供程序</span><span class="sxs-lookup"><span data-stu-id="1718c-214">How to: Create a Custom Security Token Provider</span></span>](how-to-create-a-custom-security-token-provider.md)
- [<span data-ttu-id="1718c-215">如何：创建自定义安全令牌身份验证器</span><span class="sxs-lookup"><span data-stu-id="1718c-215">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)
- [<span data-ttu-id="1718c-216">如何：创建自定义令牌</span><span class="sxs-lookup"><span data-stu-id="1718c-216">How to: Create a Custom Token</span></span>](how-to-create-a-custom-token.md)
