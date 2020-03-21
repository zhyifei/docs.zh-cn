---
title: 将 WSE 3.0 Web 服务迁移到 WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: 8f79674350109d111fe263704dee6c40c1a12451
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184569"
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>将 WSE 3.0 Web 服务迁移到 WCF
将 WSE 3.0 Web 服务迁移到 Windows 通信基础 （WCF） 的好处包括提高性能并支持其他传输、其他安全方案和 WS-* 规范。 从 WSE 3.0 迁移到 WCF 的 Web 服务的性能可高达 200% 到 400%。 有关 WCF 支持的传输的详细信息，请参阅[选择传输](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)。 有关 WCF 支持的方案的列表，请参阅[常见安全方案](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)。 有关 WCF 支持的规范的列表，请参阅[Web 服务协议互操作性指南](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md)。  
  
 以下各节提供有关如何将 WSE 3.0 Web 服务的特定功能迁移到 WCF 的指导。  
  
## <a name="general"></a>常规  
 WSE 3.0 和 WCF 应用程序包括线级互操作性和一组通用术语。 WSE 3.0 和 WCF 应用程序基于它们都支持的 WS-* 规范集，可进行线级互操作。 开发 WSE 3.0 或 WCF 应用程序时，有一组通用的术语，例如 WSE 中交钥匙安全断言的名称和身份验证模式。  
  
 尽管 WCF 和 ASP.NET 或 WSE 3.0 编程模型之间有许多类似的方面，但它们是不同的。 有关 WCF 编程模型的详细信息，请参阅[基本编程生命周期](../../../../docs/framework/wcf/basic-programming-lifecycle.md)。  
  
> [!NOTE]
> 要将 WSE Web 服务迁移到 WCF，[可以使用服务模型元数据实用程序工具 （Svcutil.exe）](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)工具生成客户端。 另一方面，该客户端还包含可以用作 WCF 服务起点的接口和类。 所生成的接口将 <xref:System.ServiceModel.OperationContractAttribute> 属性 (attribute) 应用于将 <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> 属性 (property) 设置为 `*` 的协定的成员。 当 WSE 客户端使用此设置调用 Web 服务时，将引发以下异常 **：Web.Services3.响应处理异常：WSE910：在处理响应消息期间发生错误，您可以在内部异常中找到错误**。 若要缓解此问题，可以将 <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> 属性 (attribute) 的 <xref:System.ServiceModel.OperationContractAttribute> 属性 (property) 设置为非 `null` 值，例如 `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`。  
  
## <a name="security"></a>安全性  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>使用策略文件保护其安全的 WSE 3.0 Web 服务  
 WCF 服务可以使用配置文件来保护服务，该机制类似于 WSE 3.0 策略文件。 在 WSE 3.0 中，当使用策略文件来保护 Web 服务的安全时，可以使用关守安全断言或自定义策略断言。 交钥匙安全断言与 WCF 安全绑定元素的身份验证模式紧密映射。 WCF 身份验证模式和 WSE 3.0 交钥匙安全断言不仅名称相同或类似，还使用相同的凭据类型来保护消息。 例如，WSE `usernameForCertificate` 3.0 中的交钥匙安全断言映射到 WCF 中的`UsernameForCertificate`身份验证模式。 以下代码示例演示了在 WSE 3.0 中使用`usernameForCertificate`交钥匙安全断言的最小策略如何映射到自定义`UsernameForCertificate`绑定中的 WCF 中的身份验证模式。  
  
 **WSE 3.0**  
  
```xml  
<policies>  
  <policy name="MyPolicy">  
    <usernameForCertificate messageProtectionOrder="SignBeforeEncrypt"  
                            requireDeriveKeys="true"/>  
  </policy>  
</policies>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <security authenticationMode="UserNameForCertificate"
              messageProtectionOrder="SignBeforeEncrypt"  
              requireDerivedKeys="true"/>  
  </binding>  
</customBinding>  
```  
  
 要将策略文件中指定的 WSE 3.0 Web 服务的安全设置迁移到 WCF，必须在配置文件中创建自定义绑定，并且必须将交钥匙安全断言设置为等效身份验证模式。 此外，当 WSE 3.0 客户端与服务进行通信时，必须将自定义绑定配置为使用 2004 年 8 月版 WS-Addressing 规范。 当迁移的 WCF 服务不需要与 WSE 3.0 客户端通信，并且必须仅维护安全奇偶校验时，请考虑使用具有适当安全设置的 WCF 系统定义的绑定，而不是创建自定义绑定。  
  
 下表列出了 WSE 3.0 策略文件和 WCF 中的等效自定义绑定之间的映射。  
  
|WSE 3.0 关守安全断言|WCF 自定义绑定配置|  
|----------------------------------------|--------------------------------------|  
|\<用户名 超运输安全/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<相互证书10安全/>|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<用户名用于证书安全/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<匿名证书安全/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<克伯罗斯安全/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<相互证书11安全/>|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 有关在 WCF 中创建自定义绑定的详细信息，请参阅[自定义绑定](../../../../docs/framework/wcf/extending/custom-bindings.md)。  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>使用应用程序代码保护其安全的 WSE 3.0 Web 服务  
 无论使用 WSE 3.0 还是使用 WCF，都可以在应用程序代码中指定安全要求，而不是在配置中指定。 在 WSE 3.0 中，可以通过以下方法完成此工作：创建一个派生自 `Policy` 类的类，然后通过调用 `Add` 方法添加相应的要求。 有关在代码中指定安全要求的详细信息，请参阅[：不使用策略文件保护 Web 服务](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa528763(v=msdn.10))。 在 WCF 中，要在代码中指定安全要求，请<xref:System.ServiceModel.Channels.BindingElementCollection>创建类的实例，并将<xref:System.ServiceModel.Channels.SecurityBindingElement>的实例<xref:System.ServiceModel.Channels.BindingElementCollection>添加到 。 使用 <xref:System.ServiceModel.Channels.SecurityBindingElement> 类的静态身份验证模式帮助器方法来设置安全断言需求。 有关使用 WCF 在代码中指定安全要求的详细信息，请参阅[：使用安全绑定元素创建自定义绑定](how-to-create-a-custom-binding-using-the-securitybindingelement.md)以及如何[：为指定的身份验证模式创建安全绑定元素](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)。  
  
### <a name="wse-30-custom-policy-assertion"></a>WSE 3.0 自定义策略断言  
 在 WSE 3.0 中，有两种类型的自定义策略断言：保护 SOAP 消息安全的策略断言和不保护 SOAP 消息安全的策略断言。 安全 SOAP 消息派生自 WSE 3.0`SecurityPolicyAssertion`类和 WCF 中的概念<xref:System.ServiceModel.Channels.SecurityBindingElement>等效项的策略断言是类。  
  
 需要注意的一个重要点是 WSE 3.0 交钥匙安全断言是 WCF 身份验证模式的子集。 如果在 WSE 3.0 中创建了自定义策略断言，则可能存在等效的 WCF 身份验证模式。 例如，WSE 3.0 没有提供与 `UsernameOverTransport` 关守安全断言等效的 CertificateOverTransport 安全断言，但使用 X.509 证书进行客户端身份验证。 如果您已为此方案定义了自己的自定义策略断言，则 WCF 使迁移变得简单明了。 WCF 为此方案定义了身份验证模式，因此您可以利用静态身份验证模式帮助器方法配置 WCF<xref:System.ServiceModel.Channels.SecurityBindingElement>。  
  
 如果没有 WCF 身份验证模式等效于保护 SOAP 消息的自定义策略断言、从 派生<xref:System.ServiceModel.Channels.TransportSecurityBindingElement>类<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>或<xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>WCF 类并指定等效绑定元素。 有关详细信息，请参阅[如何：使用安全绑定元素创建自定义绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)。  
  
 要转换不保护 SOAP 消息的自定义策略断言，请参阅[筛选](../../../../docs/framework/wcf/feature-details/filtering.md)和示例[自定义消息拦截器](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)。  
  
### <a name="wse-30-custom-security-token"></a>WSE 3.0 自定义安全令牌  
 用于创建自定义令牌的 WCF 编程模型与 WSE 3.0 不同。 有关在 WSE 中创建自定义令牌的详细信息，请参阅[创建自定义安全令牌](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529304(v=msdn.10))。 有关在 WCF 中创建自定义令牌的详细信息，请参阅[如何：创建自定义令牌](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)。  
  
### <a name="wse-30-custom-token-manager"></a>WSE 3.0 自定义令牌管理器  
 在 WCF 中，用于创建自定义令牌管理器的编程模型与 WSE 3.0 不同。 有关如何创建自定义令牌管理器和自定义安全令牌所需的其他组件的详细信息，请参阅[如何：创建自定义令牌](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)。  
  
> [!NOTE]
> 如果已创建自定义`UsernameToken`安全令牌管理器，WCF 提供了一种比创建自定义安全令牌管理器更容易指定身份验证逻辑的机制。 有关详细信息，请参阅[操作：使用自定义用户名和密码验证器](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)。  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>使用 MTOM 编码 SOAP 消息的 WSE 3.0 Web 服务  
 与 WSE 3 应用程序一样，WCF 应用程序可以在配置中指定 MTOM 消息编码。 要迁移此设置，>[\<将 mtomMessage 编码](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md)添加到服务的绑定中。 以下代码示例演示了如何在 WSE 3.0 中为 WCF 中的等效服务指定 MTOM 编码。  
  
 **WSE 3.0**  
  
```xml  
<messaging>  
    <mtom clientMode="On"/>  
</messaging>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <mtomMessageEncoding/>  
  </binding>  
</customBinding>  
```  
  
## <a name="messaging"></a>消息传递  
  
### <a name="wse-30-applications-that-use-the-wse-messaging-api"></a>使用 WSE 消息 API 的 WSE 3.0 应用程序  

 当使用 WSE 消息 API 来获取对在客户端和服务之间交换的 XML 的直接访问时，可以将应用程序转换为使用“Plain Old XML”(POX)。 有关 POX 的更多详细信息，请参阅[与 POX 应用程序的互操作性](interoperability-with-pox-applications.md)。 有关 WSE 消息 API 的更多详细信息，请参阅[使用 WSE 消息传递 API 发送和接收 SOAP 消息](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529293(v=msdn.10))。  
  
## <a name="transports"></a>传输  
  
### <a name="tcp"></a>TCP  
 默认情况下，使用 TCP 传输发送 SOAP 消息的 WSE 3.0 客户端和 Web 服务不与 WCF 客户端和 Web 服务互操作。 这一不兼容性是由于 TCP 协议中使用的组帧存在差异以及性能方面的原因。 但是，WCF 示例详细介绍了如何实现与 WSE 3.0 交互的自定义 TCP 会话。 有关此示例的详细信息，请参阅[传输：WSE 3.0 TCP 互操作性](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md)。  
  
 要指定 WCF 应用程序使用 TCP 传输，请使用[\<netTcp 绑定>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)。  
  
### <a name="custom-transport"></a>自定义传输协议  
 WCF 中的 WSE 3.0 自定义传输等效于通道扩展。 有关创建通道扩展的详细信息，请参阅[扩展通道图层](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)。  
  
## <a name="see-also"></a>另请参阅

- [基本编程生命周期](../../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [自定义绑定](../../../../docs/framework/wcf/extending/custom-bindings.md)
- [如何：使用 SecurityBindingElement 创建自定义绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [如何：为指定的身份验证模式创建 SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
