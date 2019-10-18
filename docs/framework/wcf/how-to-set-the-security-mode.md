---
title: 如何：设置安全模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 9b9e25cbafb6387b4584a21fd642d80bc41cd8dc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320897"
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="8c9bd-102">如何：设置安全模式</span><span class="sxs-lookup"><span data-stu-id="8c9bd-102">How to: Set the Security Mode</span></span>

<span data-ttu-id="8c9bd-103">Windows Communication Foundation （WCF）安全在大多数预定义的绑定上找到三个常见安全模式：传输、消息和 "带有消息凭据的传输"。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-103">Windows Communication Foundation (WCF) security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="8c9bd-104">另外，还有两种特定于两个绑定的模式：<xref:System.ServiceModel.BasicHttpBinding> 上的“transport-credential only”模式和 <xref:System.ServiceModel.NetMsmqBinding> 上的“Both”模式。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-104">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="8c9bd-105">不过，本主题主要讨论三种常见安全模式：<xref:System.ServiceModel.SecurityMode.Transport>、<xref:System.ServiceModel.SecurityMode.Message> 和 <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-105">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>

<span data-ttu-id="8c9bd-106">请注意，并非所有预定义绑定都支持所有这些模式。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-106">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="8c9bd-107">本主题使用 <xref:System.ServiceModel.WSHttpBinding> 和 <xref:System.ServiceModel.NetTcpBinding> 类来设置模式，并演示如何以编程方式来设置安全模式，如何通过配置来设置安全模式。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-107">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>

<span data-ttu-id="8c9bd-108">有关详细信息，请参阅 WCF 安全性、[安全概述](./feature-details/security-overview.md)、[保护服务](securing-services.md)和[保护服务和客户端](./feature-details/securing-services-and-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-108">For more information, see WCF security, see [Security Overview](./feature-details/security-overview.md), [Securing Services](securing-services.md), and [Securing Services and Clients](./feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="8c9bd-109">有关传输模式和消息的详细信息，请参阅[传输安全性](./feature-details/transport-security.md)和[消息安全性](./feature-details/message-security-in-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-109">For more information about transport mode and message, see [Transport Security](./feature-details/transport-security.md) and [Message Security](./feature-details/message-security-in-wcf.md).</span></span>

## <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="8c9bd-110">在代码中设置安全模式</span><span class="sxs-lookup"><span data-stu-id="8c9bd-110">To set the security mode in code</span></span>

1. <span data-ttu-id="8c9bd-111">创建要使用的绑定类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-111">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="8c9bd-112">有关预定义绑定的列表，请参阅[系统提供的绑定](system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-112">For a list of predefined bindings, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="8c9bd-113">此示例创建 <xref:System.ServiceModel.WSHttpBinding> 类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-113">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>

2. <span data-ttu-id="8c9bd-114">设置 `Mode` 属性所返回的对象的 `Security` 属性。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-114">Set the `Mode` property of the object returned by the `Security` property.</span></span>

     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]

     <span data-ttu-id="8c9bd-115">或者，设置为消息模式，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-115">Alternatively, set the mode to message, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]

     <span data-ttu-id="8c9bd-116">或者，设置为使用消息凭据的传输模式，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-116">Or set the mode to transport with message credentials, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]

3. <span data-ttu-id="8c9bd-117">此外，还可以在绑定的构造函数中设置模式，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-117">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]

## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="8c9bd-118">设置 ClientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="8c9bd-118">Setting the ClientCredentialType Property</span></span>

<span data-ttu-id="8c9bd-119">将模式设置为三个值之一，就确定了 `ClientCredentialType` 属性的设置方式。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-119">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="8c9bd-120">例如，使用 <xref:System.ServiceModel.WSHttpBinding> 类将模式设置为 `Transport`，意味着必须将 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> 类的 <xref:System.ServiceModel.HttpTransportSecurity> 属性设置为相应的值。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-120">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="8c9bd-121">针对传输模式设置 ClientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="8c9bd-121">To set the ClientCredentialType property for Transport mode</span></span>

1. <span data-ttu-id="8c9bd-122">创建绑定的一个实例。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-122">Create an instance of the binding.</span></span>

2. <span data-ttu-id="8c9bd-123">将 `Mode` 属性设置为 `Transport`。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-123">Set the `Mode` property to `Transport`.</span></span>

3. <span data-ttu-id="8c9bd-124">将 `ClientCredential` 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-124">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="8c9bd-125">下面的代码将该属性设置为 `Windows`。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-125">The following code sets the property to `Windows`.</span></span>

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="8c9bd-126">针对消息模式设置 ClientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="8c9bd-126">To set the ClientCredentialType property for Message mode</span></span>

1. <span data-ttu-id="8c9bd-127">创建绑定的一个实例。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-127">Create an instance of the binding.</span></span>

2. <span data-ttu-id="8c9bd-128">将 `Mode` 属性设置为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-128">Set the `Mode` property to `Message`.</span></span>

3. <span data-ttu-id="8c9bd-129">将 `ClientCredential` 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-129">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="8c9bd-130">下面的代码将该属性设置为 `Certificate`。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-130">The following code sets the property to `Certificate`.</span></span>

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="8c9bd-131">在配置中设置 Mode 和 ClientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="8c9bd-131">To set the Mode and ClientCredentialType property in configuration</span></span>

1. <span data-ttu-id="8c9bd-132">将相应的绑定元素添加到配置文件的[\<bindings >](../configure-apps/file-schema/wcf/bindings.md)元素。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-132">Add an appropriate binding element to the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="8c9bd-133">下面的示例添加了一个[\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-133">The following example adds a [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

2. <span data-ttu-id="8c9bd-134">添加一个 `<binding>` 元素，并将其 `name` 属性设置为合适的值。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-134">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="8c9bd-135">添加一个 `<security>` 元素，并将 `mode` 属性设置为 `Message`、`Transport` 或 `TransportWithMessageCredential`。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-135">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

4. <span data-ttu-id="8c9bd-136">如果模式设置为 `Transport`，则添加一个 `<transport>` 元素，并将 `clientCredential` 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-136">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>

     <span data-ttu-id="8c9bd-137">下面的示例将模式设置为 "`Transport"`，并将 `clientCredentialType` 元素的 `<transport>` 属性设置为 "`Windows"`。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-137">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="TransportSecurity">
        <security mode="Transport" >
           <transport clientCredentialType = "Windows" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="8c9bd-138">或者，将 `security mode` 设置为 "`Message"`，后接一个 `<"message">` 元素。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-138">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="8c9bd-139">本示例将 `clientCredentialType` 设置为 "`Certificate"`。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-139">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="MessageSecurity">
        <security mode="Message" >
           <message clientCredentialType = "Certificate" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="8c9bd-140">使用 <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> 值是一种特殊情况，下面将进行说明。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-140">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>

### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="8c9bd-141">使用 TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="8c9bd-141">Using TransportWithMessageCredential</span></span>

<span data-ttu-id="8c9bd-142">在将安全模式设置为 `TransportWithMessageCredential` 时，传输会确定实际提供传输级安全的机制。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-142">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="8c9bd-143">例如，HTTP 协议使用基于 HTTP 的安全套接字层 (SSL)（SSL over HTPP，或 HTTPS）。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-143">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="8c9bd-144">因此，对任何传输安全对象（例如 `ClientCredentialType`）的 <xref:System.ServiceModel.HttpTransportSecurity> 属性进行的设置都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-144">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="8c9bd-145">换言之，只能设置消息安全对象（对于 `ClientCredentialType` 绑定，则是 `WSHttpBinding` 对象）的 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-145">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>

<span data-ttu-id="8c9bd-146">有关详细信息，请参阅[如何：使用传输安全和消息凭据](./feature-details/how-to-use-transport-security-and-message-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="8c9bd-146">For more information, see [How to: Use Transport Security and Message Credentials](./feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c9bd-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c9bd-147">See also</span></span>

- [<span data-ttu-id="8c9bd-148">如何：使用 SSL 证书配置端口</span><span class="sxs-lookup"><span data-stu-id="8c9bd-148">How to: Configure a Port with an SSL Certificate</span></span>](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="8c9bd-149">如何：使用传输安全性和消息凭据</span><span class="sxs-lookup"><span data-stu-id="8c9bd-149">How to: Use Transport Security and Message Credentials</span></span>](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [<span data-ttu-id="8c9bd-150">传输安全性</span><span class="sxs-lookup"><span data-stu-id="8c9bd-150">Transport Security</span></span>](./feature-details/transport-security.md)
- [<span data-ttu-id="8c9bd-151">消息安全性</span><span class="sxs-lookup"><span data-stu-id="8c9bd-151">Message Security</span></span>](./feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="8c9bd-152">安全性概述</span><span class="sxs-lookup"><span data-stu-id="8c9bd-152">Security Overview</span></span>](./feature-details/security-overview.md)
- [<span data-ttu-id="8c9bd-153">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="8c9bd-153">System-Provided Bindings</span></span>](system-provided-bindings.md)
- [<span data-ttu-id="8c9bd-154">\<security ></span><span class="sxs-lookup"><span data-stu-id="8c9bd-154">\<security></span></span>](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [<span data-ttu-id="8c9bd-155">\<security ></span><span class="sxs-lookup"><span data-stu-id="8c9bd-155">\<security></span></span>](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [<span data-ttu-id="8c9bd-156">\<security ></span><span class="sxs-lookup"><span data-stu-id="8c9bd-156">\<security></span></span>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
