---
title: 如何：创建 WSFederationHttpBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: e54897d7-aa6c-46ec-a278-b2430c8c2e10
ms.openlocfilehash: 3a6564683a856c8d1eb47b1569f156e0b6d5cc67
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636409"
---
# <a name="how-to-create-a-wsfederationhttpbinding"></a>如何：创建 WSFederationHttpBinding

在 Windows Communication Foundation (WCF) 中，<xref:System.ServiceModel.WSFederationHttpBinding>类 ([\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)配置中) 提供了用于公开联合的服务的机制。 即，服务要求客户端使用安全令牌服务颁发的安全令牌进行身份验证。 本主题演示如何通过代码和配置来设置 <xref:System.ServiceModel.WSFederationHttpBinding>。 绑定一经创建，你就可以设置一个终结点来使用该绑定。

 基本步骤概述如下：

1. 选择一种安全模式。 <xref:System.ServiceModel.WSFederationHttpBinding> 支持 `Message`，它在消息级提供端对端的安全（即使跨多个跃点也是如此），还支持 `TransportWithMessageCredential`，它在客户端和服务可以通过 HTTPS 直接连接的情况下提供较好的性能。

    > [!NOTE]
    > <xref:System.ServiceModel.WSFederationHttpBinding> 还支持 `None` 作为安全模式。 此模式不安全，仅用于调试目的。 如果使用部署的服务终结点<xref:System.ServiceModel.WSFederationHttpBinding>其安全模式设置为`None`，生成的客户端绑定 (由生成[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)) 是<xref:System.ServiceModel.WSHttpBinding>与安全模式`None`。

     与其他系统提供的绑定不同，使用 `WSFederationHttpBinding` 时无需选择客户端凭据类型。 这是因为客户端凭据类型始终为已颁发令牌。 WCF 获取来自指定的颁发者的令牌，并将该令牌提供给服务进行身份验证客户端。

2. 在联合客户端上，将 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A> 属性设置为安全令牌服务的 URL。 将 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A> 设置为要使用的绑定，以便与安全令牌服务进行通信。

3. 可选。 将 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A> 属性设置为令牌类型的统一资源标识符 (URI)。 在联合服务上，指定服务期望使用的令牌类型。 在联合客户端上，指定客户端向安全令牌服务请求的令牌类型。

     如果未指定令牌类型，则默认情况下，客户端将在无令牌类型 URI 的情况下生成 WS-Trust 请求安全令牌 (RST)，而服务希望使用安全断言标记语言 (SAML) 1.1 令牌进行客户端身份验证。

     SAML 1.1 令牌的 URI 是`http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`。

4. 可选。 在联合服务上，将 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A> 属性设置为安全令牌服务的元数据 URL。 使用元数据终结点，服务的客户端可以选择一个适合的绑定/终结点对，前提是将服务配置为发布元数据。 有关发布元数据的详细信息，请参阅[发布元数据](publishing-metadata.md)。

 你还可以设置其他属性，包括已颁发令牌中用作校验密钥的密钥类型、在客户端和服务之间使用的算法套件、是协商还是显式指定服务凭据、服务期望已颁发令牌中包含的任何特定声明，以及必须添加到由客户端发送到安全令牌服务的请求的其他 XML 元素。

> [!NOTE]
>  仅当 `NegotiateServiceCredential` 设置为 `SecurityMode` 时，`Message` 属性才是相关的。 如果将 `SecurityMode` 设置为 `TransportWithMessageCredential`，则将忽略 `NegotiateServiceCredential` 属性。

## <a name="to-configure-a-wsfederationhttpbinding-in-code"></a>以代码方式配置 WSFederationHttpBinding

1. 创建 <xref:System.ServiceModel.WSFederationHttpBinding>的一个实例。

2. 根据需要将 <xref:System.ServiceModel.WSFederationHttpSecurity.Mode%2A> 属性设置为 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 或 <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>。 如果一个算法套件，套件以外的其他<xref:System.ServiceModel.Security.SecurityAlgorithmSuite.Basic256%2A>是必需的设置<xref:System.ServiceModel.FederatedMessageSecurityOverHttp.AlgorithmSuite%2A>属性的值来自<xref:System.ServiceModel.Security.SecurityAlgorithmSuite>。

3. 根据需要设置 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A> 属性。

4. 设置<xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A>属性设置为<xref:System.IdentityModel.Tokens.SecurityKeyType>`SymmetricKey`或。`AsymmetricKey` 所需的方式。

5. 将 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A> 属性设置为适当的值。 如果未不设置任何值，WCF 默认为`http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`，这表示 SAML 1.1 令牌。

6. 如果未指定本地颁发者则在客户端上是必需的；在服务上是可选的。 创建一个包含安全令牌服务的地址和标识信息的 <xref:System.ServiceModel.EndpointAddress>，然后将 <xref:System.ServiceModel.EndpointAddress> 实例分配给 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A> 属性。

7. 如果未指定本地颁发者则在客户端上是必需的；不能在服务上使用。 创建<xref:System.ServiceModel.Channels.Binding>有关`SecurityTokenService`，并将分配<xref:System.ServiceModel.Channels.Binding>实例向<xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A>属性。

8. 不能在客户端上使用；在服务上可选。 为安全令牌服务的元数据创建一个 <xref:System.ServiceModel.EndpointAddress> 实例，然后将其分配给 `IssuerMetadataAddress` 属性。

9. 在客户端和服务上都是可选的。 创建一个或多个 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement> 实例，并将其添加到 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A> 属性返回的集合中。

10. 在客户端和服务上都是可选的。 创建一个或多个 <xref:System.Xml.XmlElement> 实例，并将其添加到 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A> 属性返回的集合中。

## <a name="to-create-a-federated-endpoint-in-configuration"></a>在配置中创建联合终结点

1. 创建[ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)的小孩[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)应用程序配置文件中的元素。

2. 创建[\<绑定 >](../../../../docs/framework/misc/binding.md)的子元素[ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)并设置`name`属性为适当的值。

3. 创建`<security>`的子元素[\<绑定 >](../../../../docs/framework/misc/binding.md)元素。

4. 根据需要将 `mode` 元素的 `<security>` 属性设置为 `Message` 或 `TransportWithMessageCredential` 的一个值。

5. 创建一个 `<message>` 元素，作为 `<security>` 元素的子元素。

6. 可选。 将 `algorithmSuite` 元素的 `<message>` 属性设置为适当的值。 默认值为 `Basic256`。

7. 可选。 如果需要非对称校验密钥，请将 `issuedKeyType` 元素的 `<message>` 属性设置为 `AsymmetricKey`。 默认值为 `SymmetricKey`。

8. 可选。 设置 `issuedTokenType` 元素的 `<message>` 属性。

9. 如果未指定本地颁发者则在客户端上是必需的；在服务上是可选的。 创建一个 `<issuer>` 元素，作为 `<message>` 元素的子元素。

10. 将 `address` 属性设置为 `<issuer>` 元素，并指定安全令牌服务接受令牌请求的地址。

11. 可选。 添加一个 `<identity>` 子元素，并指定安全令牌服务的标识。

12. 有关详细信息，请参阅[服务标识和身份验证](service-identity-and-authentication.md)。

13. 如果未指定本地颁发者则在客户端上是必需的；不能在服务上使用。 创建[\<绑定 >](../../../../docs/framework/misc/binding.md)可用于与安全令牌服务进行通信的绑定部分中的元素。 有关创建绑定的详细信息，请参阅[如何：在配置中指定服务绑定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)。

14. 通过设置 `binding` 元素的 `bindingConfiguration` 和 `<issuer>` 属性，来指定在上一步创建的绑定。

15. 不能在客户端上使用；在服务上可选。 创建`<issuerMetadata>`的子元素 <`message`> 元素。 然后，在 `address` 元素的 `<issuerMetadata>` 属性中，指定安全令牌服务将要发布其元数据的地址。 还可以选择添加一个 `<identity>` 子元素，并指定安全令牌服务的标识。

16. 在客户端和服务上都是可选的。 添加一个 `<claimTypeRequirements>` 元素，将其作为 `<message>` 元素的子元素。 指定必选和可选声明，该服务依赖于通过添加[\<添加 >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)元素`<claimTypeRequirements>`元素和指定声明类型与`claimType`属性。 通过设置 `isOptional` 属性来指定给定的声明是必选的还是可选的。

## <a name="example"></a>示例

下面的代码示例演示强制设置 `WSFederationHttpBinding` 的代码。

[!code-csharp[c_FederationBinding#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_federationbinding/cs/source.cs#2)]
[!code-vb[c_FederationBinding#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_federationbinding/vb/source.vb#2)]

## <a name="see-also"></a>请参阅

- [联合](federation.md)
- [联合示例](../../../../docs/framework/wcf/samples/federation-sample.md)
- [如何：禁用安全会话在 WSFederationHttpBinding 上](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
